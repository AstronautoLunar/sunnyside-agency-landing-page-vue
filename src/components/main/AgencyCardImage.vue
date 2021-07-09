<template>
    <div 
        class="AgencyCardImage"
    >
        <slot name="background-image">

        </slot>
        <article class="article" role="article">
            <slot>

            </slot>
        </article>
    </div>
</template>

<script>
    export default {
        name: "AgencyCardImage",
        components: {

        }
    }
</script>

<style scoped>
    div.AgencyCardImage {
        width: 50%;
        height: 38vw;

        position: relative;
    }

    article.article {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        
        width: 100%;

        position: absolute;
        left: 50%;
        bottom: -20%;
        transform: translate(-50%, -50%);
    }
</style>