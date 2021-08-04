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
        width: 50%;
        height: 38vw;

        position: relative;
    }

    div.AgencyCardImage, article.article {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    article.article {
        flex-direction: column;
        
        width: 100%;
    }
    
    img.image-card {
        width: 100%;
    
        position: absolute;
        top: 0;
        left: 0;
    }

    @media screen and (max-width: 809px) {
        p.paragraphy-card-image {
            width: auto;
        }
    }
</style>