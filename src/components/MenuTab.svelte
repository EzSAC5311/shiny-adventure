<div class="menu-tab">
  <div class="menu">
    <p class="menu-item">Contact</p>
    <div class="menu-content" />
  </div>
  <div class="menu">
    <p class="menu-item">Discord</p>
    <div class="menu-content" />
  </div>
</div>

<style>
  .menu-tab {
    display: flex;
    margin: auto 1rem;
    gap: 2rem;
  }
  .menu-item {
    position: relative;
    display: inline-block;
    cursor: pointer;
  }

  .menu-item::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background-color: black;
    border-radius: 0.1rem;
    transform: scaleX(0);
    transition: transform 0.3s ease;
  }

  .menu-item:hover::after {
    transform: scaleX(1);
  }
</style>
