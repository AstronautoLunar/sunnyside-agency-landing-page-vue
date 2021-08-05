<template>
    <header id="AgencyHeader">
        <span id="logo">
            sunnyside
        </span>
        <div 
            id="nav-menu-desktop"
            v-show="showMenuDesktop"
        >
            <nav id="navigation-buttons">
                <AgencyHeaderButton
                    v-for="button in buttonsHeader"
                    :key="button.id"
                    :textName="button.text"
                    :typeButton="button.type"
                />
            </nav>
        </div>
        <div
            v-show="!showMenuDesktop"
            id="nav-menu-mobile"
            @click="toggleWindowMenu"
        >
            <div id="menu-mobile">
                <div class="line">
                </div>
                <div class="line">
                </div>
                <div class="line">
                </div>
            </div>
        </div>
    </header>
    <div 
        id="window-menu-mobile"
        v-show="showWindowMenu"
    >
        <div id="menu-buttons">
            <div id="triangle">

            </div>
        </div>
    </div>
</template>

<script>
    import AgencyHeaderButton from '../header/AgencyHeaderButton.vue';

    export default {
        name: "AgencyHeader",
        components: {
            AgencyHeaderButton,
        },
        data() {
            return {
                buttonsHeader: [
                    {
                        id: 1,
                        text: "About",
                        type: "normal",
                    },
                    {
                        id: 2,
                        text: "Services",
                        type: "normal",
                    },
                    {
                        id: 3,
                        text: "Projects",
                        type: "normal",
                    },
                    {
                        id: 4,
                        text: "Contact",
                        type: "strong",
                    }
                ],
                mediaQuerieList: matchMedia("(max-width: 650px)"),
                showMenuDesktop: true,
                showWindowMenu: false,
            }
        },
        methods: {
            createMenuHeader(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.showMenuDesktop = false;
                } else {
                    this.showMenuDesktop = true;
                    this.showWindowMenu = false;
                }
            },
            toggleWindowMenu() {
                this.showWindowMenu = !this.showWindowMenu;
            }
        },
        mounted() {
            const mediaQuerieLoading = this.mediaQuerieList;

            this.createMenuHeader(mediaQuerieLoading);

            mediaQuerieLoading.addListener(this.createMenuHeader)
        }
    }

</script>

<style scoped>

    header#AgencyHeader {
        width: 100%;
        height: 100px;

        justify-content: space-between;

        position: absolute;
        top: 0;
    }

    span#logo {
        font-size: 30px;

        color: var(--white);

        margin-left: 30px;
    }

    nav#navigation-buttons, 
    header#AgencyHeader,
    div#menu-mobile {
        display: flex;
        align-items: center;
    }

    nav#navigation-buttons {
        justify-content: center;
    }

    div#nav-menu-desktop, div#menu-mobile {
        margin-right: 30px;
    }

    div#menu-mobile {
        flex-direction: column;
        justify-content: center;
    }

    div#menu-mobile > div.line {
        width: 30px;
        height: 2px;

        background-color: rgba(255, 255, 255, 0.8);

        margin-bottom: 5px;
    }

    div#menu-mobile > div.line:last-of-type {
        margin-bottom: 0;
    }


    div#window-menu-mobile {
        position: absolute;
        top: 210px;
        left: 50%;
        transform: translate(-50%, -50%);

        width: 100%;

        display: flex;
        justify-content: center;
    }

    div#triangle {
        width: 0;
        height: 0;
        border: 50px solid;
        border-right-color: #ffffff;
        border-left-color: transparent;
        border-top-color: transparent;
        border-bottom-color: transparent;

        position: absolute;
        top: -20%;
        right: 0%;
    }

    div#menu-buttons {
        width: calc(100% - 50px);
        height: 200px;

        background-color: #ffffff;

        position: relative;
    }
</style>