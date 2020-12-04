<script>
  let oversee = [
    { description: "Landscapers", id: 1 },
    { description: "Maintenance companies", id: 2 },
    { description: "Major projects", id: 3 },
    { description: "Deliveries", id: 4 },
  ];
  let monitor = [
    { description: "Security systems", id: 5 },
    { description: "Heating and cooling controls", id: 6 },
    { description: "Lighting", id: 7 },
    { description: "Pest control needs", id: 8 },
  ];
  let misc = [
    { description: "Run faucets and toilets", id: 9 },
    { description: "Start and run your vehicle(s)", id: 10 },
    { description: "Perform minor necessary repairs", id: 11},
    { description: "Clear debris", id: 12 },
  ];
  let services = [
    { name: "Monitoring", contents: monitor },
    { name: "Overseeing", contents: oversee },
    { name: "General care", contents: misc },
  ];
</script>

<section class="services-wrapper" aria-label="Services">
  <h2>Our services include</h2>
  <div class="card-wrapper">
    {#each services as service, index (index)}
      <div class="card">
        <h3 id={index}>{service.name}</h3>
        <ul aria-labelledby={index}>
          {#each service.contents as item (item.id)}
            <li>{item.description}</li>
          {/each}
        </ul>
      </div>
    {/each}
  </div>
  <p>
    The services listed here are just a sampling of what we can do for you. If
    you have other needs,
   <em>just ask</em>.
  </p>
</section>

<style>
  .services-wrapper {
    background-color: white;
    width: 100%;
    margin: 0;
    padding: 1rem 0;
    position: relative;
    z-index: 1;
  }
  .card-wrapper {
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
    align-items: center;
  }
  .card {
    flex: 1;
    width: calc(17rem + 10vw);
    background-color: #bacaec;
    border-radius: 5px;
    box-shadow: 5px 10px 10px gray;
    margin: 2rem;
  }
  h2 {
    margin: 0 auto;
    max-width: 75%;
  }
  
  h3 {
    font-size: 2rem;
    margin-bottom: 0;
  }
  ul {
    display: inline-block;
    padding-left: 1.5rem;
    margin: 1rem auto;
    margin-bottom: 2rem;
    line-height: 1.5rem;
    text-align: left;
  }
  li {
    padding: 0.5rem;
  }
  p {
    text-align: center;
    margin: 1rem auto;
    line-height: 1.5rem;
    width: 80%;
  }
  @media (min-width: 1035px) {
    .services-wrapper {
      min-height: calc(100vh - 8rem);
    }
    .card-wrapper {
      display: flex;
      flex-flow: row wrap;
      justify-content: space-around;
      align-items: stretch;
      margin: auto;
    }
    .card {
      max-width: 21rem;
    }
    p {
      width: 33%;
    }
  }
</style>