<script>
  // @ts-nocheck

  import "bootstrap/dist/css/bootstrap.min.css";
  import "./style.css";
  import "../ProactNavbar.svelte";
  import { initializeApp } from "firebase/app";
  import { collection, getDocs, getFirestore } from "firebase/firestore";
  import ProactNavbar from "../ProactNavbar.svelte";

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
  const buyerDB = collection(db, "buyerDB");

  getDocs(buyerDB).then((s) => {
    console.log(s.docs.length);
    // console.log(s.docs);
  });
</script>

<body style="background-color: #FAEAEE; height: 100vh;">
  <ProactNavbar />
  <div class="container mt-5">
    <div class="row mt-5">
      {#await getDocs(buyerDB) then s}
        {#each s.docs as data}
          <div class="col-lg-4 mt-4">
            <div class="box">
              <h1>
                {data["_document"]["data"]["value"]["mapValue"]["fields"][
                  "title"
                ].stringValue}
              </h1>
              <br />
              <h3>
                {data["_document"]["data"]["value"]["mapValue"]["fields"][
                  "name"
                ].stringValue}
              </h3>
              <br />
              <h3>
                {data["_document"]["data"]["value"]["mapValue"]["fields"][
                  "number"
                ].integerValue}
              </h3>
            </div>
          </div>
        {/each}
      {/await}
    </div>
  </div>
</body>
