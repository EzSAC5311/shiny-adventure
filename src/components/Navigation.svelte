<script>
  import MenuTab from "./MenuTab.svelte";
  let isOpen = true;
  window.onscroll = function () {
    if (this.oldScroll > this.scrollY) {
      isOpen = true;
    } else {
      isOpen = false;
    }
    this.oldScroll = this.scrollY;
  };
</script>

<nav>
  <div class="container" style="--slide: {isOpen ? '.5rem' : '-6rem'}">
    <div class="company">
      <img
        class="company-image"
        src="https://cdn.discordapp.com/attachments/888298091487305739/992826872935219210/animation_640_l5432hge.gif"
        alt="mc-gif"
        width="50px"
      />
      <p class="company-name">MC-LOHAPHAN</p>
    </div>
    <MenuTab />
  </div>
</nav>

<style lang="scss">
  nav {
    position: fixed;
    width: 100%;
    display: flex;
    z-index: 999;
  }
  .container {
    background-color: white;
    display: flex;
    justify-content: space-between;
    margin: 1rem auto;
    border-radius: 0.5rem;
    box-shadow: rgba(0, 0, 0, 0.08) 0px 4px 12px;
    transform: translateY(var(--slide));
    transition: transform 0.2s ease;
    width: 60%;
    padding: 0.5rem 1rem;
  }
  .company {
    display: flex;
    gap: 1rem;
  }
  .company-image {
    border-radius: 0.2rem;
  }
  .company-name {
    font-weight: bold;
    cursor: url(https://abs.twimg.com/emoji/v2/72x72/1f525.png) 36 36, auto;
  }
</style>
