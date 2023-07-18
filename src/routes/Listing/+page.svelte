<script>
  // import "bootstrap/dist/js/bootstrap.bundle.min.js";
  import ProactNavbar from "../ProactNavbar.svelte";
  import "bootstrap/dist/css/bootstrap.min.css";
  import "../Register/style.css";

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
  <ProactNavbar />
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
  </div>
</body>
