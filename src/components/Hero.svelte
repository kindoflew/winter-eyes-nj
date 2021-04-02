<script>
  import { fade } from "svelte/transition";
  import { onMount } from "svelte";

  //Snow animation lovingly stolen from the Svelte tutorial
  let characters = ["*", "."];
  let snow = new Array(100)
    .fill()
    .map((_, i) => {
      return {
        character: characters[i % characters.length],
        x: Math.random() * 97,
        y: -20 - Math.random() * 100,
        r: 0.1 + Math.random() * 1.3,
      };
    })
    .sort((a, b) => a.r - b.r);

  let ready = false;

  onMount(() => {
    ready = true;
    let frame;

    function loop() {
      frame = requestAnimationFrame(loop);

      snow = snow.map((flake) => {
        flake.y += 0.2 * flake.r;
        if (flake.y > 115) {
          flake.y = -115;
          flake.x = Math.random() * 97;
        }
        return flake;
      });
    }

    loop();

    return () => cancelAnimationFrame(frame);
  });
</script>

<section>
  {#each snow as s}
    <span
      style="left: {s.x}%; top: {s.y}%; transform: scale({s.r})"
      aria-hidden="true">{s.character}</span
    >
  {/each}
  {#if ready}
    <div in:fade={{ duration: 900 }}>
      <h1>Winter Eyes</h1>
      <p>Property Caretakers / Estate Managers</p>
      <p>"<em>Our eyes are your eyes.</em>"</p>
    </div>
  {/if}
</section>

<style>
  section {
    background-color: #bacaec;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-family: "Oswald", sans-serif;
    position: relative;
    overflow: hidden;
  }
  h1 {
    font-size: calc(5rem + 3vw);
    font-weight: 300;
    margin: 0;
    line-height: 1.1;
    position: relative;
    z-index: 1;
  }
  p {
    font-size: calc(1rem + 0.5vw);
    margin: 0;
    position: relative;
    z-index: 1;
  }
  em {
    font-size: calc(1rem + 0.5vw);
    margin-top: 2.5rem;
    line-height: 2.5rem;
    text-align: center;
    width: 90%;
    position: relative;
    z-index: 1;
  }
  span {
    position: absolute;
    padding: 0;
    margin: 0;
    font-size: 2.5rem;
    font-family: "Nixie One", cursive;
    color: white;
    z-index: 0;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }
  @media (min-width: 795px) {
    section {
      height: 100vh;
      justify-content: center;
    }
    span {
      font-size: 2.75em;
    }
  }
</style>
