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
        src="./assets/mobile/image-transform.jpg"
        alt="image egg main"
      />
      <img
        class="image-main"
        src="./assets/mobile/image-stand-out.jpg"
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
        <AgencyCardImage
          v-for="card in agencyCardImage"
          :key="card.id"
          :backgroundImageSrc="card.backgroundImageSrc"
          :title="card.title"
          :paragraphy="card.paragraphy"
        >
        </AgencyCardImage>
      </section>
      <section id="cards-client-area">
        <h2>CLIENT TESTIMONIALS</h2>
        <div id="cards-clients">
          <AgencyCardClient
            v-for="( user, index ) in userComments"
            :key="index"
            :img-user="user.srcImage"
            :comments-text="user.comments"
            :name-user="user.userName"
            :profession="user.profession"
          />
        </div>
      </section>
      <div id="images-spotlight">
        <img
          src="./assets/desktop/image-gallery-milkbottles.jpg"
          alt="image galley milkbottle"
        />
        <img
          src="./assets/desktop/image-gallery-orange.jpg"
          alt="image galley orange"
        />
        <img
          src="./assets/desktop/image-gallery-cone.jpg"
          alt="image gallery cone"
        />
        <img
          src="./assets/desktop/image-gallery-sugarcubes.jpg"
          alt="image gallery sugarcubes"
        />
      </div>
    </main>
    <footer id="footer" role="footer">
      <h1
        id="title-footer"
      >sunnyside</h1>
      <div id="area-links-text-footer">
        <a
          class="links-footer"
          href="#"
          v-for="( linkText, index ) in linksTextFooter"
          :key="index"
        >{{ linkText }}</a>
      </div>
      <div id="area-links-icon-footer">
        <a href="#">
          <img
            src="./assets/icon-facebook.svg"
            alt="link icon facebook"
          />
        </a>
        <a href="#">
          <img
            src="./assets/icon-instagram.svg"
            alt="link icon facebook"
          />
        </a>
        <a href="#">
          <img
            src="./assets/icon-twitter.svg"
            alt="link icon facebook"
          />
        </a>
        <a href="#">
          <img
            src="./assets/icon-pinterest.svg"
            alt="link icon facebook"
          />
        </a>
      </div>
    </footer>
  </div>
</template>

<script>
  import AgencyHeader from './components/header/AgencyHeader.vue';
  import AgencyCard from './components/main/AgencyCard.vue';
  import AgencyCardImage from './components/main/AgencyCardImage.vue';
  import AgencyCardClient from './components/main/AgencyCardClient.vue';

  export default {
    name: 'App',
    components: {
      AgencyHeader,
      AgencyCard,
      AgencyCardImage,
      AgencyCardClient,
    },
    data() {
      return {
        userComments: [
          {
            srcImage: "image-emily.jpg",
            comments: "We put our trust in Sunnyside and they delivered, making sure our needs were met and deadlines were always hit.",
            userName: "Emily R.",
            profession: "Marketing Director"
          },
          {
            srcImage: "image-thomas.jpg",
            comments: "Sunnyside´s enthusiasm coupled with their keen interest in our brand's success made it a satisfying and enjoyable experience.",
            userName: "Thomas S.",
            profession: "Chief Operating Officer"
          },
          {
            srcImage: "image-jennie.jpg",
            comments: "Incredible end result! Our sales increased over 400% when we worked with Sunnyside. Highly recommended!",
            userName: "Jennie F.",
            profession: "Business Owner"
          },
        ],
        linksTextFooter: [ 
          "About", 
          "Services", 
          "Projects" 
        ],
        agencyCardImage: [
          {
            id: 1,
            backgroundImageSrc: "image-graphic-design.jpg",
            title: "Graphic Design",
            paragraphy: "Great design makes you memorable. We deliver artwork that underscores your brand message and captures potential clients´ attention",
          },
          {
            id: 2,
            backgroundImageSrc: "image-photography.jpg",
            title: "Photography",
            paragraphy: "Increase your credibility by getting the most stunning, high-quality photos that improve your business image.",
          }
        ],
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
    position: relative;

    justify-content: center;
  }

  div#app, footer#footer {
    flex-direction: column;
    align-items: center;
  }

  div#app, 
  main#main, 
  section.cards-image, 
  section#cards-client-area,
  div#cards-clients,
  div#images-spotlight,
  footer#footer,
  div#area-links-text-footer,
  div#area-links-icon-footer
  {
    display: flex;
  }

  div#background-main {
    background-image: url(./assets/desktop/image-header.jpg);
    background-size: cover;
    background-position: center 100%;

    height: 700px;

    position: relative;
  }

  div#background-main, 
  div#app,
  div#cards-clients,
  div#images-spotlight,
  main#main, 
  section#cards-client-area,
  section.cards-image,
  footer#footer
  {
    width: 100%;
  }

  img#arrow {
    bottom: 35%;
  }

  img#arrow, 
  span#text-background-main 
  {
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
  h2.title-card-image, 
  p.paragraphy-card-image,
  section#cards-client-area
  {
    font-family: Fraunces, Helvetica, Arial;
  }

  p.paragraph-card {
    color: var(--dark-grayish-blue);

    margin-bottom: 45px;
  }

  img.image-main {
    object-fit: cover;

    width: 50%;
    height: 38vw;
  }

  section.cards-image {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }

  section#cards-client-area {
    flex-direction: column;
    justify-content: center;

    padding: 150px 125px 100px;
    box-sizing: border-box;
  }

  section#cards-client-area > h2 {
    color: var(--grayish-blue);

    letter-spacing: 10px;

    font-size: 15px;

    margin-bottom: 50px;

    text-align: center;
  }

  section#cards-client-area,
  div#cards-clients,
  div#area-links-text-footer,
  div#area-links-icon-footer
  {
    align-items: center;
  }

  div#cards-clients,
  div#area-links-text-footer,
  div#area-links-icon-footer
  {
    justify-content: space-around;
  }

  div#images-spotlight > img {
    width: 25%;
  }

  footer#footer {
    height: 300px;

    background-color: var(--dark-moderate-cyan);

    justify-content: space-evenly;
  }

  div#area-links-text-footer 
  {
    width: 400px;
  }

  h1#title-footer {
    margin: 0;
  }

  h1#title-footer, 
  a.links-footer 
  {
    color: var(--dark-desaturated-cyan);
  }

  a.links-footer {
    text-decoration: none;
  }

  div#area-links-text-footer {
    margin-bottom: 50px;
  }

  div#area-links-icon-footer {
    width: 150px;
  }

  @media screen and (max-width: 942px) {
    main#main {
      flex-direction: column;
      justify-content: center;
    }

    img.image-main {
      width: 100%;
    }

    h1.title-card, p.paragraph-card {
      text-align: center;
    }

    div#cards-clients {
      flex-direction: column;
    }

    section#cards-client-area {
      padding: 150px 0 100px;
    }
  }
</style>
