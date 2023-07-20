<script>
  // @ts-nocheck

  import ProactNavbar from "../ProactNavbar.svelte";
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

  getDocs(sellerDB).then((s) => {
    // console.log(s.docs.length);
    console.log(s.docs);
  });
</script>

<body style="background-color: #FAEAEE;">
  <ProactNavbar />
  <div class="container">
    <div id="books-container" class="row mt-5">
      {#await getDocs(sellerDB) then s}
        {#each s.docs as data}
          <div class="col-lg-4 col-12 mt-4">
            <div class="card h-100">
              <img
                src={data["_document"]["data"]["value"]["mapValue"]["fields"][
                  "image"
                ].stringValue}
                alt=""
                class="card-img-top h-50"
              />
              <div class="card-body h-50">
                <h1 class="card-title">
                  {data["_document"]["data"]["value"]["mapValue"]["fields"][
                    "title"
                  ].stringValue}
                </h1>
                <h1 class="card-subtitle">
                  {data["_document"]["data"]["value"]["mapValue"]["fields"][
                    "number"
                  ].integerValue}
                </h1>
                <h1 class="card-text">
                  ₹ {data["_document"]["data"]["value"]["mapValue"]["fields"][
                    "price"
                  ].integerValue}
                </h1>
              </div>
            </div>
          </div>
        {/each}
      {/await}
    </div>
  </div>
</body>
