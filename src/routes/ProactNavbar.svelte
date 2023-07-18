<script>
  import AddPageCard from "./AddPageCard.svelte";
</script>

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
          data-bs-dismiss="modal"
          aria-label="Close"
        >
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <AddPageCard />
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal"
          >Close</button
        >
        <button type="button" class="btn btn-primary">Submit</button>
      </div>
    </div>
  </div>
</div>

<style>
  /* Add any custom styles here */
</style>
