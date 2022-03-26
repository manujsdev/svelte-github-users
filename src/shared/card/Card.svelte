<div class="card">
  <slot>Content card..</slot>
</div>

<style>
  .card {
    margin: 2em;
    box-shadow: 0 4px 8px 0 rgb(0 0 0 / 20%);
    transition: 0.3s;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
  }  
</style>
