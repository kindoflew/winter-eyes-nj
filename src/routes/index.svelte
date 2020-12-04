<script>
  import Header from '../components/Header.svelte';
  import Hero from '../components/Hero.svelte';
  import Services from '../components/Services.svelte';
  import About from '../components/About.svelte';
  import Contact from '../components/Contact.svelte';
  import Footer from '../components/Footer.svelte';
  let services;
  let about;
  let contact;
  let sections;
  
  function handleScroll(event) {                //header height is 6rem
    let currentSection = sections[event.detail] - getRemInPx(6);
    window.scrollTo({
      top: currentSection,
      behavior: 'smooth'
    });  
  }
  function getRemInPx(num) {
    let fontSize = window.getComputedStyle(document.documentElement).getPropertyValue('font-size');
    return parseFloat(fontSize) * num;
  }
  function sectionCoords() {
    sections = {
      'Services': getTop(services),
      'About': getTop(about),
      'Contact': getTop(contact), 
    }
  }
  function getTop(node){
    return node.getBoundingClientRect().top + window.pageYOffset;
  }  
</script>

<svelte:window on:resize={sectionCoords} on:load={sectionCoords} />

<Header on:sendScroll={handleScroll} />

<main>
  <Hero />
  <!--Wrap components in divs so I can reference them for coordinates-->
  <div bind:this={services}>
    <Services />
  </div>

  <div bind:this={about}>
    <About />
  </div>

  <div bind:this={contact}>
    <Contact />
  </div>
</main>

<Footer />

<style>
  main {
    text-align: center;
  }
</style>
