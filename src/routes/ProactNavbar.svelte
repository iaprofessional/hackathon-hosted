<script>
  // @ts-nocheck
  import { initializeApp } from "firebase/app";
  import { collection, getFirestore, addDoc } from "firebase/firestore";
  import {
    getStorage,
    ref as sRef,
    uploadBytesResumable,
    getDownloadURL,
  } from "firebase/storage";

  // Variables to control the visibility of the elements
  let c1Visible = "inline";
  let c2Visible = "none";

  function toggle1() {
    console.log("Onclick");
    console.log(Sellector);
    // Function to toggle the visibility of elements based on 'checked'
    if (Sellector == false) {
      c1Visible = "none";
      c2Visible = "inline";
      Sellector = true;
    } else {
      c1Visible = "inline";
      c2Visible = "none";
      Sellector = false;
    }
  }

  const firebaseConfig = {
    apiKey: "AIzaSyCeBCVVfalGWO03XNkJy8F1hJsII6Lgjb0",
    authDomain: "practice-5c982.firebaseapp.com",
    databaseURL: "https://practice-5c982-default-rtdb.firebaseio.com",
    projectId: "practice-5c982",
    storageBucket: "practice-5c982.appspot.com",
    messagingSenderId: "664592348370",
    appId: "1:664592348370:web:4385f2b327bbc5562aa90b",
  };
  initializeApp(firebaseConfig);

  const db = getFirestore();

  const sellerDB = collection(db, "sellerDB");
  const buyerDB = collection(db, "buyerDB");

  let Sellector = false;
  var files = [];
  var fileURL;
  var output;

  function handleFileChange(event) {
    files = event.target.files;
    const file = files[0];
    console.log(file);
    const extension = getFileEXT(file);
    const name = getFileName(file);
    console.log("name & ext: " + name + " & " + extension);
    // Call your file processing or upload function here
    fileURL = URL.createObjectURL(file);
    console.log(fileURL);
  }

  function getFileEXT(file) {
    var temp = file.name.split(".");
    var ext = temp.slice(temp.length - 1, temp.length);
    output = "." + ext[0];
    return output;
  }

  function getFileName(file) {
    var temp = file.name.split(".");
    var fname = temp.slice(0, -1).join(".");
    return fname;
  }

  function Loading() {
    document.getElementById("modal").innerHTML =
      "<div class='spinner-border' role='status'><span class='sr-only'>Loading...</span></div>";
  }

  let ST = "";
  var SP = "";
  var Snumber = "";

  var BT = "";
  var Bnumber = "";
  var BN = "";
  var downloadURL;
  async function UploadP() {
    // Loading();
    var image = files[0];
    var imgName = ST + output;
    const storage = getStorage();
    const stRef = sRef(storage, imgName);
    const UT = uploadBytesResumable(stRef, image);
    UT.on(
      "state_changed",
      (snapshot) => {
        var pro = (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
        console.log(pro);
      },
      (error) => {
        console.log(error);
      }
    );

    try {
      await UT;
      downloadURL = await getDownloadURL(UT.snapshot.ref);
    } catch (error) {
      console.log(error);
    }
    update();
  }

  function update() {
    if (Sellector == false) {
      if (ST != "" && SP != "" && Snumber != "") {
        addDoc(sellerDB, {
          price: SP,
          image: downloadURL,
          number: Snumber,
          title: ST,
        }).then(() => {
          ST = "";
          SP = "";
          Snumber = "";
          alert("Pls close the box and refresh site");
        });
      } else {
        alert("All input required");
      }
    } else {
      if (BN != "" && BT != "" && Bnumber != "") {
        addDoc(buyerDB, {
          number: Bnumber,
          title: BT,
          name: BN,
        }).then(() => {
          BT = "";
          BN = "";
          Bnumber = "";
          alert("Pls close the box and refresh site");
        });
      } else {
        alert("All input required");
      }
    }
  }
</script>

<nav class="navbar navbar-expand-md navbar-dark bg-dark text-white fixed-top">
  <div class="container">
    <a class="navbar-brand" href="/Home">LVISN</a>
    <button
      class="navbar-toggler"
      data-bs-toggle="collapse"
      data-bs-target="#nav"
    >
      <span class="navbar-toggler-icon" />
    </button>
    <div class="collapse navbar-collapse" id="nav">
      <center>
        <ul class="navbar-nav">
          <li class="nav-item">
            <a href="Home" class="nav-link">Home</a>
          </li>
          <li class="nav-item">
            <a href="/Store" class="nav-link">Store</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/Register">Register Requirement</a>
          </li>
          <br />
          <button
            class="btn btn-primary"
            type="button"
            data-bs-toggle="modal"
            data-bs-target="#exampleModal">Add +</button
          >
        </ul>
      </center>
    </div>
  </div>
</nav>

<div
  class="modal fade"
  id="exampleModal"
  tabindex="-1"
  role="dialog"
  aria-labelledby="exampleModalLabel"
  aria-hidden="true"
>
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Enter data</h5>
        <button
          type="button"
          class="close"
          data-bs-dismiss="modal"
          aria-label="Close"
        >
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body" id="modal">
        <div>
          <div class="card">
            <center>
              <h1>Buyer or Seller?</h1>
              <br />
              <div class="form-check">
                <label class="form-check-label">
                  <input
                    class="form-check-input"
                    type="checkbox"
                    on:click={toggle1}
                  />
                  Buyer
                </label>
              </div>
            </center>
            <center id="c1" style="display: {c1Visible};" class="card-body">
              <input
                class="form-control input-md border-black border-3"
                placeholder="Book Title"
                bind:value={ST}
              />
              <br />
              <h2>Book's Image</h2>
              <br />
              <div class="row">
                <input
                  type="file"
                  on:change={handleFileChange}
                  class="form-control-file"
                  accept="image/png,image/jpeg"
                />
              </div>

              <br />

              <input
                id="i2"
                class="form-control border-black border-3"
                placeholder="Price"
                type="number"
                bind:value={SP}
              />
              <br />

              <input
                id="i3"
                class="form-control input-md border-black border-3"
                placeholder="Contact: +91 xxxxxxxxxx"
                type="number"
                bind:value={Snumber}
              />
              <br />
            </center>
            <center id="c2" style="display: {c2Visible}; " class="card-body">
              <input
                class="form-control input-sm"
                style="border-width: medium; border-color: black; width: 80%;"
                placeholder="Title of book you want"
                bind:value={BT}
              />
              <br />
              <input
                class="form-control input-sm"
                style="border-width: medium; border-color: black; width: 80%;"
                placeholder="Contact: +91 xxxxxxxxxx"
                type="number"
                bind:value={Bnumber}
              />
              <br />
              <input
                id="b3"
                class="form-control input-sm"
                style="border-width: medium; border-color: black; width: 80%;"
                placeholder="Name"
                bind:value={BN}
              />
              <br />
            </center>
          </div>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal"
          >Close</button
        >
        <button type="button" class="btn btn-primary" on:click={UploadP}
          >Submit</button
        >
      </div>
    </div>
  </div>
</div>

<style>
  /* Add any custom styles here */
</style>
