<template>
    <div 
        class="AgencyCardImage"
    >
        <img
            class="image-card"
            :src="require(`../../assets/desktop/${backgroundImageSrc}`)"
            alt="image graphic design"
        />
        <article class="article" role="article">
            <h2 class="title-card-image">{{ title }}</h2>
            <p class="paragraphy-card-image">
                {{ paragraphy }}
            </p>
        </article>
    </div>
</template>

<script>
    export default {
        name: "AgencyCardImage",
        components: {

        },
        props: {
            backgroundImageSrc: {
                type: String,
                required: true,
            },
            title: {
                type: String,
                required: true,
            },
            paragraphy: {
                type: String,
                required: true,
            }
        }
    }
</script>

<style scoped>
    div.AgencyCardImage {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        
        width: 50%;
        height: 38vw;

        position: relative;
    }

    img.image-card {
        width: 100%;
        height: 38vw;
    
        object-fit: cover;

        position: absolute;
        top: 0;
        left: 0;
    }

    article.article {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        
        width: 100%;

        margin-bottom: 40px;
    }
    
    h2.title-card-image {
        margin: 0;
    }

    h2.title-card-image, p.paragraphy-card-image {
        opacity: 0.6;

        text-align: center;
    }

    p.paragraphy-card-image {
        margin: 30px;

        line-height: 30px;
    }

    @media screen and (max-width: 942px) {
        p.paragraphy-card-image {
            width: auto;
        }
    }

    @media screen and (max-width: 886px) {
        div.AgencyCardImage, 
        img.image-card 
        {
            width: 100%;
            height: 150vw;
        }

        article.article {
            margin-bottom: 15vw;
        }
    }

    @media screen and (max-width: 410px) {
        article.article {
            margin-bottom: 5vw;
        }
    }
</style>