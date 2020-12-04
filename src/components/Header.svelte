<script>
  import NavBar from "./NavBar.svelte";
  
  let scrollY;
  function topScroll() {
    window.scrollTo({
      top: 0,
      behavior: 'smooth'
    });
    document.activeElement.blur();
  }
</script>

<svelte:window bind:scrollY={scrollY} />

<header class:filled={scrollY > 0}>
  <div class="logo-wrapper">
    <img
      src="winter-eyes-glasses-small-filled.png"
      alt="Old man winter in sunglasses - click to return to top"
      on:click={topScroll}
      tabindex="0"
      role="link"
      on:keyup={(e) => e.key === 'Enter' && topScroll()}
    />
  </div>

  <NavBar on:sendScroll />
</header>

<style>
  header {
    margin: 0;
    background-color: transparent;
    display: flex;
    justify-content: space-between;
    position: fixed;
    z-index: 2;
    top: 0;
    left: 0;
    right: 0;
    box-shadow: none;
    transition: background-color 0.3s, box-shadow 0.3s, height 0.3s linear;
  }
  .filled {
    background-color:  #bacaec;
    box-shadow: 1px 2px 5px gray;
    height: 6rem;
  }
  img {
    width: auto;
    height: 6rem;
  }
  img:hover {
    cursor: pointer;
  }
  .logo-wrapper {
    align-self: flex-start;
    display: flex;
    font-size: 0.8rem;
    margin-left: 0.5rem;
  }
  @media (min-width: 795px) {
    header {
      height: 10rem;
    }
    .logo-wrapper {
      font-size: 1rem;
      margin-top: 1rem;
      margin-left: 1rem;
    }
    img {
      height: 8.5rem;
      width: auto;
    }
  }
</style>