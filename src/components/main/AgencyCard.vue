<template>
    <section class="AgencyCard">
        <article>
            <slot name="title">

            </slot>
            <slot name="paragraph">

            </slot>
            <div class="area-link">
                <a 
                    ref="linkCard"
                    class="link" 
                    href="#"
                    style="opacity: 1;"
                    @mouseenter="         
                        colorBorderRender = `background-color: ${colorBorder};`"
                    @mouseout="
                        colorBorderRender = 
                        `background-color: ${
                        colorBorder}; opacity: 0.2;`;"
                >LEARN MORE</a>
                <div 
                    class="line-link"
                    :style="colorBorderRender"
                ></div>

            </div>
        </article>
    </section>
</template>

<script>
    export default {
        name: "AgencyCard",
        components: {

        },
        props: {
            colorBorder: {
                type: String,
                required: true,
            }
        },
        data() {
            return {
                colorBorderRender: `background-color: ${this.colorBorder}; opacity: 0.2;`,
            }
        }
    }
</script>

<style scoped>
    section.AgencyCard {
        width: 50%;
        height: 38vw;

        display: flex;
        justify-content: center;
        align-items: center;
    }

    section.AgencyCard > article {
        width: 400px;
    }

    h5, p, a {
        font-family: Fraunces, Helvetica, Arial;
    }

    div.area-link {
        position: relative;

        width: 150px;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        position: relative;

        margin-bottom: 40px;
    }

    div.line-link {
        width: 150px;
        height: 10px;

        background-color: black;

        border-radius: 20px;
    }

    a.link {
        text-decoration: none;

        color: var(--black);

        position: absolute;
        top: -12px;
    }

    /* Adaptações de tela */

    @media screen and (max-width: 942px) {
        section.AgencyCard, 
        section.AgencyCard > article 
        {
            width: 100%;
        }

        section.AgencyCard {
            height: 100vw;
        }

        section.AgencyCard > article {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            box-sizing: border-box;
            padding: 20px;
        }
    }
</style>