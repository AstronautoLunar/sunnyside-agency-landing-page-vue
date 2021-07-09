<template>
    <div class="AgencyCardClient">
        <img
            class="img-user"
            :src="require(`../../assets/${imgUser}`)"
            alt="user comments"
        />
        <span class="comments">
            {{ commentsText }}
        </span>
        <div class="about-user">
            <strong>
                {{ nameUser }}
            </strong>
            <span class="profession">
                {{ profession }}
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "AgencyCardClient",
        components: {

        },
        props: {
            imgUser: {
                type: String,
                required: true,
            },
            commentsText: {
                type: String,
                required: true,
            },
            nameUser: {
                type: String,
                required: true,
            },
            profession: {
                type: String,
                required: true,
            },
        }
    }
</script>

<style scoped>
    div.AgencyCardClient {
        
        height: 400px;
    }

    div.AgencyCardClient > span {
        text-align: center;
    }

    img.img-user {
        width: 60px;
        height: 60px;
        
        border-radius: 100%;
    }

    span.comments {
        color: var(--very-dark-grayish-blue);

        width: 90%;

        line-height: 32.5px;
    }

    span.profession {
        color: var(--grayish-blue);
    }

    div.AgencyCardClient, 
    div.about-user 
    {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }

    div.about-user > strong {
        margin-bottom: 10px;
    }

    div.about-user > span.profession {
        font-size: 11px;
    }
</style>