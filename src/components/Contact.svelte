<script>
</script>

<section class="contact-wrapper" aria-label="Contact">
  <h2>Contact us today for rates customized to your needs.</h2>
  <div class="button-wrapper">
    <a href="tel:+17325473769">
      <svg width="1em" height="1em" viewBox="0 0 16 16" class="phone" fill="currentColor" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path fill-rule="evenodd" d="M3.654 1.328a.678.678 0 0 0-1.015-.063L1.605 2.3c-.483.484-.661 1.169-.45 1.77a17.568 17.568 0 0 0 4.168 6.608 17.569 17.569 0 0 0 6.608 4.168c.601.211 1.286.033 1.77-.45l1.034-1.034a.678.678 0 0 0-.063-1.015l-2.307-1.794a.678.678 0 0 0-.58-.122l-2.19.547a1.745 1.745 0 0 1-1.657-.459L5.482 8.062a1.745 1.745 0 0 1-.46-1.657l.548-2.19a.678.678 0 0 0-.122-.58L3.654 1.328zM1.884.511a1.745 1.745 0 0 1 2.612.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.678.678 0 0 0 .178.643l2.457 2.457a.678.678 0 0 0 .644.178l2.189-.547a1.745 1.745 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.634 18.634 0 0 1-7.01-4.42 18.634 18.634 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877L1.885.511z"/>
      </svg>
      732-547-3769
    </a>
    <a href="mailto:lebrer1960@gmail.com">
      <svg width="1em" height="1em" viewBox="0 0 16 16" class="email" fill="currentColor" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path fill-rule="evenodd" d="M0 4a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V4zm2-1a1 1 0 0 0-1 1v.217l7 4.2 7-4.2V4a1 1 0 0 0-1-1H2zm13 2.383l-4.758 2.855L15 11.114v-5.73zm-.034 6.878L9.271 8.82 8 9.583 6.728 8.82l-5.694 3.44A1 1 0 0 0 2 13h12a1 1 0 0 0 .966-.739zM1 11.114l4.758-2.876L1 5.383v5.73z"/>
      </svg>
      Email us
    </a>
  </div>
</section>

<style>
  .contact-wrapper {
    background-color: white;
    min-height: calc(100vh - 18rem);
    padding: 3rem 0;
  }
  .button-wrapper {
    display: flex;
    flex-flow: column;
    align-items: center;
    justify-content: flex-start;
    margin: auto;
  }
  h2 {
    font-size: 1.5rem;
    font-family: 'Ubuntu', sans-serif;
    margin: 1rem auto;
    margin-bottom: 2rem;
  }
  a {
    border-style: none;
    color: #333;
    background-color: #bacaec;
    border-radius: 5px;
    box-shadow: 5px 10px 10px gray;
    font-size: 1.5rem;
    width: 15rem;
    padding: 1rem;
    margin: 1rem;
    transition: background-color 0.5s;
    position: relative;
  }
  a:hover {
    cursor: pointer;
    text-decoration: none;    
  }
  a:active {
    box-shadow: 2px 5px 5px gray;
    transform: scale(95%);
  }
  svg {
    height: 1.875rem;
    width: 1.875rem;
    position: absolute;
    top: 0.94rem;
    left: 0.94rem;
  }
  @media (min-width: 795px) {
    .contact-wrapper {
      min-height: calc(100vh - 16rem);
      padding-bottom: 1rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .button-wrapper {
      justify-content: center;
    }
    h2 {
      margin-bottom: 0;
    }
    a:hover {
      background-color: #8AAAEC; 
    }
  }
</style>