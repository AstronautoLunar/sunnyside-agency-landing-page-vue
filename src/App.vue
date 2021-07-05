<template>
  <div id="app">
      <div id="background-main">
        <span id="text-background-main">
          WE ARE CREATIVES
        </span>
        <img
          id="arrow"
          src="./assets/icon-arrow-down.svg"
          alt="arrow background image"
        />
      </div>
    <AgencyHeader/>
    <main id="main" role="main">
      <AgencyCard
        colorBorder="hsl(51, 100%, 49%)"
      >
        <template #title>
          <h1 class="title-card">Transform your brand</h1>
        </template>
        <template #paragraph>
          <p class="paragraph-card">We are a full-service agency specializing in helping brands grow fast. Engage your clients through compelling visuals that do most of the marketing for you.</p>
        </template>
      </AgencyCard>
      <img
        class="image-main"
        src="./assets/desktop/image-transform.jpg"
        alt="image egg main"
      />
      <img
        class="image-main"
        src="./assets/desktop/image-stand-out.jpg"
        alt="image glass main"
      />
      <AgencyCard
        colorBorder="hsl(7, 99%, 70%)"
      >
        <template #title>
          <h1 class="title-card">Stand out to the right audience</h1>
        </template>
        <template #paragraph>
          <p class="paragraph-card">Using a collaborative formula of designers, researchers, photographers, videographers, and copywriters, we'll build and extend your brand in digital places.</p>
        </template>
      </AgencyCard>
      <section 
        class="section cards-image" 
        role="section"
      >
        <AgencyCardImage>
          <template #background-image>
            <img
              class="image-card"
              src="./assets/desktop/image-graphic-design.jpg"
              alt="image graphic design"
            />
          </template>
          <h2 class="title-card-image">Graphic Design</h2>
          <p class="paragraphy-card-image">
            Great design makes you memorable. We deliver artwork that underscores your brand message and captures potential clients´ attention
          </p>
        </AgencyCardImage>
        <AgencyCardImage>
          <template #background-image>
            <img
              class="image-card"
              src="./assets/desktop/image-photography.jpg"
              alt="image graphic design"
            />
          </template>
          <h2 class="title-card-image">Photography</h2>
          <p class="paragraphy-card-image">
            Increase your credibility by getting the most stunning, high-quality photos that improve your business image.
          </p>
        </AgencyCardImage>
      </section>
    </main>
  </div>
</template>

<script>
  import AgencyHeader from './components/AgencyHeader.vue';
  import AgencyCard from './components/AgencyCard.vue';
  import AgencyCardImage from './components/AgencyCardImage.vue';

  export default {
    name: 'App',
    components: {
      AgencyHeader,
      AgencyCard,
      AgencyCardImage,
    }
  }

</script>

<style>
  :root {
    /* Primary */
    --soft-red: hsl(7, 99%, 70%);
    --yellow: hsl(51, 100%, 49%);
    --dark-desaturated-cyan: hsl(167, 40%, 24%);
    --dark-blue: hsl(198, 62%, 26%);
    --dark-moderate-cyan: hsl(168, 34%, 41%);
    --black: #000000;
  
    /* Neutral */
    --very-dark-desaturated-blue: hsl(212, 27%, 19%);
    --very-dark-grayish-blue: hsl(213, 9%, 39%);
    --dark-grayish-blue: hsl(232, 10%, 55%);
    --grayish-blue: hsl(210, 4%, 67%);
    --white: hsl(0, 0%, 100%);
  }

  body {
    margin: 0;
    padding: 0;

    font-family: Barlow, Helvetica, Arial;
  }

  div#app {
    width: 100%;

    position: relative;

    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  div#app, main#main, section.cards-image {
    display: flex;
  }

  div#background-main {
    background-image: url(./assets/desktop/image-header.jpg);
    background-size: cover;
    background-position: center 100%;

    height: 700px;

    position: relative;
  }

  div#background-main, main#main {
    width: 100%;
  }

  img#arrow {
    bottom: 35%;
  }

  img#arrow, span#text-background-main {
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  span#text-background-main {
    color: var(--white);

    top: 25%;

    letter-spacing: 7px;

    text-align: center;

    font-size: 50px;
  }

  h1.title-card {
    font-size: 35px;
    font-weight: bold;

    width: 350px;

    margin-bottom: 35px;
  }
  
  main#main {
    flex-wrap: wrap;
  }

  span#text-background-main, 
  h1.title-card, 
  p.paragraph-card,
  h2.title-card-image, p.paragraphy-card-image
  {
    font-family: Fraunces, Helvetica, Arial;
  }

  p.paragraph-card {
    color: var(--dark-grayish-blue);

    margin-bottom: 45px;
  }

  img.image-main {
    width: 50%;
  }

  section.cards-image {
    width: 100%;
  }

  img.image-card {
    position: absolute;
    top: 0;
    left: 0;

    width: 100%;
  }

  h2.title-card-image {
    font-size: 30px;
  }

  h2.title-card-image, p.paragraphy-card-image {
    text-align: center;

    opacity: 0.6;
  }

  p.paragraphy-card-image {
    width: 400px;

    line-height: 25px;
  }
</style>
