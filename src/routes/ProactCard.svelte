<script>
  export let title;
  export let subtitle;
  export let text;
  export let image;
</script>

<div class="col-lg-4 col-12 mt-4">
  <div class="card">
    <img src={image} alt="" class="card-img-top" />
    <div class="card-body">
      <h1 class="card-title">{title}</h1>
      <h1 class="card-subtitle">{subtitle}</h1>
      <h1 class="card-text">{text}</h1>
    </div>
  </div>
</div>

<style>
  /* Add any custom styles here */
</style>
