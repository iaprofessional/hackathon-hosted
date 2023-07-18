<script>
  // @ts-nocheck

  // @ts-nocheck

  // imports
  // import "bootstrap/dist/js/bootstrap.bundle.min.js";
  import AddPageCard from "../AddPageCard.svelte";
  import "bootstrap/dist/css/bootstrap.min.css";
  import "../Register/style.css";
  import { initializeApp } from "firebase/app";
  import { collection, getDocs, getFirestore } from "firebase/firestore";

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

  // getDocs(sellerDB).then((s) => {
  // 	console.log(s.docs.length);
  // 	console.log(s.docs);
  // });

  let data;
</script>

<body class="bg-black">
  <nav class="navbar navbar-expand-md navbar-dark bg-dark text-white fixed-top">
    <div class="container">
      <a class="navbar-brand" href="/Home">Brand Name</a>
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
            <li class="nav-item active">
              <a href="/Store" class="nav-link active">Store</a>
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
            data-dismiss="modal"
            aria-label="Close"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <AddPageCard />
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal"
            >Close</button
          >
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>
    </div>
  </div>
  <div class="container">
    <div id="books-container" class="row mt-5">
      {#await getDocs(sellerDB) then s}
        {#each s.docs as data}
          <div class="col-lg-4 col-12 mt-4">
            <div class="card">
              <img
                src={data["_document"]["data"]["value"]["mapValue"]["fields"][
                  "image"
                ].stringValue}
                alt=""
                class="card-img-top"
              />
              <div class="card-body">
                <h1 class="card-title">{data.id}</h1>
                <h1 class="card-subtitle">
                  {data["_document"]["data"]["value"]["mapValue"]["fields"][
                    "number"
                  ].stringValue}
                </h1>
                <h1 class="card-text">
                  {data["_document"]["data"]["value"]["mapValue"]["fields"][
                    "price"
                  ].stringValue}
                </h1>
              </div>
            </div>
          </div>
        {/each}
      {/await}
    </div>
  </div>
</body>
