<template>
    <button 
        class="AgencyHeaderButton"
        :style="styleButton"
        ref="button"   
    >
        <span :style="styleStrong.color">{{ 
            typeButton === "strong" 
            ? 
            textName.toUpperCase() 
            : 
            textName 
        }}</span>
    </button>
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
                },
            }
        },
        computed: {
            styleButton() {
                return `${this.styleStrong.backgroundColor} ${this.styleStrong.fontFamily} ${this.styleStrong.padding}`
            }
        },
        beforeMount() {
            switch(this.typeButton) {
                case "normal": 
                default: 
                    this.styleStrong.backgroundColor = "";
                    this.styleStrong.color = "";
                    this.styleStrong.fontFamily = "font-family: Barlow, Helvetica, Arial;";
                    this.styleStrong.padding = "";
                    break;
                case "strong":
                    this.styleStrong.backgroundColor = "background-color: var(--white);";
                    this.styleStrong.color = "color: #000000;";
                    this.styleStrong.fontFamily = "font-family: Fraunces, Helvetica, Arial;";
                    this.styleStrong.padding = "padding: 15px 25px;";
                    break;
            }
        },
        mounted() {
            let buttonMounted = this.$refs.button;
            let styleMounted = this.styleStrong;

            if(this.typeButton === "strong") {
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
    button.AgencyHeaderButton {
        background-color: transparent;
        color: var(--white);

        border: none;
        
        outline: none;
        box-shadow: none;

        display: flex;
        justify-content: center;
        align-items: center;

        margin: 0 20px;

        border-radius: 30px;

        font-size: 15px;

        transition: all 0.2s;
    }
</style>