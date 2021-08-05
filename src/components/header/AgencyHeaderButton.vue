<template>
    <div 
        class="AgencyHeaderButton"
        :style="styleButton"
        ref="button"   
    >
        <a 
            :style="styleStrong.color"
            href="#"
            class="linkButtonDesktop"
        >{{ 
            typeButton === "strong" 
            ? 
            textName.toUpperCase() 
            : 
            textName 
        }}</a>
    </div>
</template>

<script>
    export default {
        name: "AgencyHeaderButton",
        components: {

        },
        props: {
            textName: {
                type: String,
                required: true,
            },
            typeButton: {
                type: String,
                required: true,
            }
        },
        data() {
            return {
                styleStrong: {
                    backgroundColor: "",
                    color: "",
                    fontFamily: "",
                    padding: "",
                    textTransform: "",
                    fontSize: "",
                },
            }
        },
        computed: {
            styleButton() {
                return `${this.styleStrong.backgroundColor} ${this.styleStrong.fontFamily} ${this.styleStrong.padding} ${this.styleStrong.textTransform} ${this.styleStrong.fontSize}`
            }
        },
        beforeMount() {
            switch(this.typeButton) {
                case "normal-desktop": 
                default: 
                    this.styleStrong.backgroundColor = "";
                    this.styleStrong.color = "";
                    this.styleStrong.fontFamily = "font-family: Barlow, Helvetica, Arial;";
                    this.styleStrong.padding = "";
                    break;

                case "strong-desktop":
                    this.styleStrong.backgroundColor = "background-color: var(--white);";
                    this.styleStrong.color = "color: #000000;";
                    this.styleStrong.fontFamily = "font-family: Fraunces, Helvetica, Arial;";
                    this.styleStrong.padding = "padding: 15px 25px;";
                    this.styleStrong.textTransform = "text-transform: uppercase;";
                    break;

                case "normal-mobile": 
                    this.styleStrong.backgroundColor = "";
                    this.styleStrong.color = "color: hsla(211, 28%, 19%, 0.705);";
                    this.styleStrong.fontFamily = "font-family: Barlow, Helvetica, Arial;";
                    this.styleStrong.padding = "";
                    this.styleStrong.fontSize = "font-size: 20px;";
                    break;

                case "strong-mobile":
                    this.styleStrong.backgroundColor = "background-color: var(--yellow);";
                    this.styleStrong.color = "color: var(--black);";
                    this.styleStrong.fontFamily = "font-family: Fraunces, Helvetica, Arial;";
                    this.styleStrong.padding = "padding: 15px 25px;";
                    this.styleStrong.textTransform = "text-transform: uppercase;";
                    this.styleStrong.fontSize = "font-size: 20px;";
                    break;
            }
        },
        mounted() {
            let buttonMounted = this.$refs.button;
            let styleMounted = this.styleStrong;

            if(this.typeButton === "strong-desktop") {
                buttonMounted.addEventListener('mouseenter', () => {
                    styleMounted.backgroundColor = "background-color: rgba(255, 255, 255, 0.3);";
                    styleMounted.color = "";
                }, true)

                buttonMounted.addEventListener('mouseout', () => {
                    styleMounted.backgroundColor = "background-color: var(--white);"
                    styleMounted.color = "color: #000000;";
                })
            }
        }
    }
</script>

<style scoped>
    div.AgencyHeaderButton {
        background-color: transparent;
        color: var(--white);

        display: flex;
        justify-content: center;
        align-items: center;

        margin: 0 20px;

        border-radius: 30px;

        font-size: 15px;

        transition: all 0.2s;

        cursor: pointer;
    }

    a.linkButtonDesktop {
        text-decoration: none;

        color: inherit;
    }
</style>