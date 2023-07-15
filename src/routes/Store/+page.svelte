<script>
  // import "bootstrap/dist/js/bootstrap.bundle.min.js";
  import "bootstrap/dist/css/bootstrap.min.css";
  import "../Register/style.css";
  const data = [
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 1",
      number: "+91 12345 67890",
      price: "$10",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 2",
      number: "+91 12345 67890",
      price: "$15",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 3",
      number: "+91 12345 67890",
      price: "$20",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 4",
      number: "+91 12345 67890",
      price: "$25",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 5",
      number: "+91 12345 67890",
      price: "$30",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 6",
      number: "+91 12345 67890",
      price: "$100",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 7",
      number: "+91 12345 67890",
      price: "$10",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 8",
      number: "+91 12345 67890",
      price: "$15",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 9",
      number: "+91 12345 67890",
      price: "$20",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 10",
      number: "+91 12345 67890",
      price: "$25",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 11",
      number: "+91 12345 67890",
      price: "$30",
    },
    {
      image:
        "https://imgtr.ee/images/2023/07/15/cb47bcc078cd3e751128c23540fc55e2.png",
      title: "Item 12",
      number: "+91 12345 67890",
      price: "$100",
    },
  ];
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
              <a href="/Store " class="nav-link active">Store</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/Register">Register Requirement</a>
            </li>
            <br />
            <button class="btn btn-primary">Add +</button>
          </ul>
        </center>
      </div>
    </div>
  </nav>
  <div class="container">
    <div id="books-container" class="row mt-5">
      {#each data as i}
        <div class="col-md-4 col-12 mt-4">
          <div class="card">
            <img src={i.image} alt="" class="card-img-top" />
            <div class="card-body">
              <h1 class="card-title">{i.title}</h1>
              <h1 class="card-subtitle">{i.number}</h1>
              <h1 class="card-text">{i.price}</h1>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</body>
