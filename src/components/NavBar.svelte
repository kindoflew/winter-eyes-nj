<script>
  import { createEventDispatcher, onMount } from "svelte";
  import { slide, fade } from "svelte/transition";

  const dispatch = createEventDispatcher();
  let open = false;
  let width;

  //fixes FOUT
  let ready;
  onMount(() => {
    ready = true;
  });

  let sections = [
    { name: "Services", id: 1 },
    { name: "About", id: 2 },
    { name: "Contact", id: 3 },
  ];

  function sendScroll(name) {
    if (width < 795) toggleOpen();
    dispatch("sendScroll", name);
  }

  function toggleOpen() {
    open = !open;
    document.body.classList.toggle("open");
  }
</script>

<svelte:window bind:innerWidth={width} />

{#if ready}
  <nav>
    {#if width < 795}
      {#if open}
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 30 30"
          width="30"
          height="30"
          on:click={toggleOpen}
          tabindex="0"
          role="button"
          aria-label="Menu"
          aria-expanded="true"
          on:keyup={(e) => e.key === 'Enter' && toggleOpen()}
          transition:fade="{{duration: 100}}"
        >
          <line x1="2" y1="2" x2="28" y2="28" stroke="#333" stroke-width="5" />
          <line x1="28" y1="2" x2="2" y2="28" stroke="#333" stroke-width="5" />
        </svg>

        <ul transition:slide>
          {#each sections as section (section.id)}
            <li
              on:click={() => sendScroll(section.name)}
              tabindex="0"
              role="link"
              on:keyup={(e) => e.key === 'Enter' && sendScroll(section.name)}
            >
              {section.name}
            </li>
          {/each}
        </ul>
      {:else}
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 30 30"
          width="30"
          height="30"
          on:click={toggleOpen}
          tabindex="0"
          role="button"
          aria-label="Menu"
          aria-expanded="false"
          on:keyup={(e) => e.key === 'Enter' && toggleOpen()}
          transition:fade="{{duration: 100}}"
        >
          <line x1="0" y1="5" x2="30" y2="5" stroke="#333" stroke-width="5" />
          <line x1="0" y1="15" x2="30" y2="15" stroke="#333" stroke-width="5" />
          <line x1="0" y1="25" x2="30" y2="25" stroke="#333" stroke-width="5" />
        </svg>
      {/if}
    {:else}
      <ul>
        {#each sections as section (section.id)}
          <li
            on:click={() => sendScroll(section.name)}
            tabindex="0"
            role="link"
            on:keyup={(e) => e.key === 'Enter' && sendScroll(section.name)}
          >
            {section.name}
          </li>
        {/each}
      </ul>
    {/if}
  </nav>
{/if}

<style>
  ul {
    height: 104vh;
    width: 100vw;
    list-style: none;
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    z-index: 9;
    position: absolute;
    top: -2.5rem;
    right: 0;
    background-color: #bacaec;
    box-shadow: 5px 10px 10px gray;
  }
  li {
    font-size: 1.5rem;
    margin: 2rem;
  }
  li:hover {
    text-decoration: underline;
    cursor: pointer;
  }
  svg {
    height: 40px;
    width: 40px;
    position: absolute;
    top: 30px;
    right: 14px;
    padding: 0;
    margin: 0;
    border-style: none;
    background-color: transparent;
    z-index: 10;
    cursor: pointer;
  }
  @media (min-width: 795px) {
    nav {
      width: 25%;
      position: relative;
      z-index: 9;
    }
    ul {
      width: 100%;
      height: 6rem;
      margin-right: 1rem;
      padding: 0;
      margin: 0;
      list-style: none;
      display: flex;
      flex-flow: row;
      justify-content: space-between;
      align-items: center;
      position: static;
      background-color: transparent;
      box-shadow: none;
    }
    li {
      margin: 0 auto;
      font-size: 1rem;
    }
    li:hover {
      text-decoration: underline;
      cursor: pointer;
    }
  }
</style>
