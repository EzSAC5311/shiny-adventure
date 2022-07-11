<script>
  function handleClick() {
    window.location.assign("https://github.com/EzSAC5311/shiny-adventure");
  }
</script>

<div class="box">
  <div class="fix-box">
    <div class="flex-box">
      <button class="btn-custom" on:click={handleClick}>Github</button>
    </div>
  </div>
</div>

<style>
  .box {
    display: flex;
    height: 100vh;
    justify-content: center;
    align-items: center;
    color: white;
  }
  .fix-box {
    position: fixed;
  }
  .flex-box {
    display: flex;
  }
  .btn-custom {
    cursor: pointer;
    outline: none;
    border: 0;
    border-radius: 0.1rem;
    outline: 1px solid rgb(228, 88, 38);
    outline-offset: 0.2rem;
    width: 10rem;
    height: 3rem;
    background-color: rgb(240, 165, 0);
    color: white;
  }
  .btn-custom:hover {
    background-color: rgb(240, 165, 0, 0.9);
  }
</style>
