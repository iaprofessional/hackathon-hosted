<script>
  import ProactNavbar from "../ProactNavbar.svelte";
  import "bootstrap/dist/css/bootstrap.min.css";
  import "../Register/style.css";
</script>

<body style="background-color: #FAEAEE;">
  <!-- svelte-ignore a11y-distracting-elements -->
  <b>
    <marquee
      class="mt-3"
      bgcolor="#C65097"
      style="font-size: 30px ; color: #FAEAEE;"
      >Flat 90% discount!
    </marquee>
  </b>
  <center style="background-color: #FAEAEE;">
    <ProactNavbar />
    <br />
    <br />
    <div class="container mt-md-0 mt-5">
      <div class="card">
        <div class="card-body">
          <div class="vstack">
            <img
              src="https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png"
              class="fluid-img rounded d-block"
              alt="90% off"
            />
            <br />
            <h1>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni,
              est?
            </h1>
            <br />
            <p class="lead display-6">
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ducimus
              odio nostrum laudantium deleniti sed quaerat quibusdam neque
              dolorem voluptas illo!
            </p>
            <br />
            <h1>Finding target audiences made easy</h1>
            <br />
            <p>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ducimus
              accusamus error quo sapiente, maiores suscipit?
            </p>
          </div>
        </div>
      </div>
    </div>
  </center>
</body>
