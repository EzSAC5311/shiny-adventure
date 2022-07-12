<script>
  import { onMount } from "svelte";

  let contributor_list = [];

  onMount(async () => {
    const res = await fetch(
      "https://api.github.com/repos/EzSAC5311/shiny-adventure/contributors"
    );
    const data = await res.json();
    contributor_list = data.map((item) => {
      return {
        name: item.login,
        avatar: item.avatar_url,
      };
    });
  });
</script>

<div class="contributor">
  <div class="contributor-title">
    <code class="underline-animation">Contributor</code>
  </div>
  <div class="contributor-list">
    {#each contributor_list as item}
      <img alt={item.name} src={item.avatar} class="contributor-image" />
    {/each}
  </div>
</div>

<style lang="scss">
  .contributor {
    position: relative;
    height: 100vh;
    background-color: rgb(57, 62, 70);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .contributor-title {
    font-size: 3rem;
    margin-bottom: 2rem;
    color: rgb(0, 173, 181);
  }

  .contributor-list {
    display: flex;
    flex-wrap: wrap;
    border-radius: 3rem;
  }

  .contributor-image {
    border: 3px solid white;
    border-radius: 50%;
    background-size: cover;
    background-repeat: no-repeat;
    height: 5rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px,
      rgba(0, 0, 0, 0.22) 0px 10px 10px;

    &:nth-child(n + 2) {
      margin-left: -1.5rem;
    }
  }

  .underline-animation {
    position: relative;
    display: inline-block;
    cursor: pointer;

    &::after {
      content: "";
      width: 100%;
      height: 0.2rem;
      position: absolute;
      bottom: 0;
      left: 0;
      background: rgb(238, 238, 238);
      border-radius: 0.2rem;
      transform: scaleX(0);
      transform-origin: bottom right;
      transition: transform 0.3s ease-in-out;
    }

    &:hover::after {
      transform: scaleX(1);
      transform-origin: bottom left;
    }
  }
</style>
