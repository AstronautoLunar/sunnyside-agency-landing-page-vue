<template>
  <main id="app">
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
  </main>
</template>

<script>
  import AgencyHeader from './components/AgencyHeader.vue';

  export default {
    name: 'App',
    components: {
      AgencyHeader,
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

  main#app {
    width: 100%;

    position: relative;
  }

  div#background-main {
    background-image: url(./assets/desktop/image-header.jpg);
    background-size: cover;
    background-position: center 100%;

    width: 100%;
    height: 700px;
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
    
    font-family: Fraunces, Helvetica, Arial;

    top: 25%;

    letter-spacing: 7.5px;

    text-align: center;

    font-size: 50px;
  }
</style>
