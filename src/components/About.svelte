<script>
</script>

<section aria-label="About">
  <h2>Integrity. Security. Reliability.</h2>
  <div class="about-wrapper">
    <div class="image-wrapper">
      <img src="andy-small.jpeg" alt="Andrew Maroney, owner." />
    </div>
    <p>
      Winter Eyes is a family-owned business proudly serving the Shore area of
      Monmouth County, NJ. Our owner, Andrew Maroney, has over 27 years of Law Enforcement
      experience. You can trust us to provide the utmost care and attention when
      you are away - long or short term. We are fully insured and bonded.
    </p>
  </div>
</section>

<style>
  section {
    background-color:#bacaec;
    margin: 0;
    padding: 1rem 0;
  }
  .about-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: auto;
  }
  h2 {
    margin: 0;
  }
  p {
    line-height: 1.5rem;
    text-align: center;
    margin: 0 2rem;
    padding-bottom: 2rem;
  }
  .image-wrapper {
    height: 12rem;
    width: 10rem;
    margin: 1rem 0 2rem 0;
  }
  img {
    height: 100%;
    width: auto;
    border-radius: 4px;
    box-shadow: 5px 10px 10px gray;
  }
  @media (min-width: 740px) {
    section {
      min-height: calc(100vh - 8rem);
    }
    .about-wrapper {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: flex-start;
      width: 75vw;
      margin: auto;
      padding-top: 3.5rem;
    }
    p {
      max-width: 24rem;
      font-size: 1.2rem;
      text-align: left;
      margin: 0 1rem;
    }
    .image-wrapper {
      margin-top: 0;
      margin-bottom: 0;
      height: 18rem;
      width: 15rem;
    }
    img {
      height: 100%;
      width: auto;
    }
  }
</style>