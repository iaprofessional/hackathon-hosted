<script>
  // import "bootstrap/dist/js/bootstrap.bundle.min.js";
  import "bootstrap/dist/css/bootstrap.min.css";
  import "./style.css";

  const data = [
    {
      name: "sample",
      title: "Item 1",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 2",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 3",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 4",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 5",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 6",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 7",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 8",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 9",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 10",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 11",
      number: "+91 12345 67890",
    },
    {
      name: "sample",
      title: "Item 12",
      number: "+91 12345 67890",
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
        <ul class="navbar-nav">
          <li class="nav-item">
            <a href="/Home" class="nav-link">Home</a>
          </li>

          <li class="nav-item active">
            <a href="/Store " class="nav-link">Store</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" href="/Register">Register Requirement</a>
          </li>
          <br />
          <button class="btn btn-primary">Add +</button>
        </ul>
      </div>
    </div>
  </nav>

  <div class="container mt-5">
    <div class="row mt-5">
      {#each data as i}
        <div class="col-md-3 mt-4">
          <div class="box">
            <h1>{i.title}</h1>
            <br />
            <h3>{i.name}</h3>
            <br />
            <h3>{i.number}</h3>
          </div>
        </div>
      {/each}
    </div>
  </div></body
>
