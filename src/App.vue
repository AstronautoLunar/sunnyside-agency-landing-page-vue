<template>
  <div id="app">
    <AgencyHeader/>
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
    <div id="quite">
      <AgencyCard
        colorBorder="blue"
      >
        <template #title>
          <h1 class="title-card">Transform your brand</h1>
        </template>
        <template #paragraph>
          <p class="paragraph-card">We are a full-service agency specializing in helping brands grow fast. Engage your clients through compelling visuals that do most of the marketing for you.</p>
        </template>
      </AgencyCard>
    </div>
  </div>
</template>

<script>
  import AgencyHeader from './components/AgencyHeader.vue';
  import AgencyCard from './components/AgencyCard.vue';

  export default {
    name: 'App',
    components: {
      AgencyHeader,
      AgencyCard,
    },
    data() {
      return {
        cards: [
          {
            id: 1,
            title: "",
            paragraph: ""
          },
          {
            id: 2,
            title: "Stand out to the right audience",
            paragraph: "Using a collaborative formula of designers, researchers, photographers, videographers, and copywriters, we'll build and extend your brand in digital places."
          }
        ]
      }
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

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  div#background-main {
    background-image: url(./assets/desktop/image-header.jpg);
    background-size: cover;
    background-position: center 100%;

    height: 700px;
  }

  div#background-main, div#quite {
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
  
  span#text-background-main, 
  h1.title-card, 
  p.paragraph-card {
    font-family: Fraunces, Helvetica, Arial;
  }

  p.paragraph-card {
    color: var(--dark-grayish-blue);

    margin-bottom: 45px;
  }
</style>
