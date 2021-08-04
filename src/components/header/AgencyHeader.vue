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
            v-show="showMenuMobile"
        >
            <h1>Hello World</h1>
        </div>
    </header>
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
                showMenuMobile: false,
            }
        },
        methods: {
            createMenuHeader(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.showMenuDesktop = false;
                    this.showMenuMobile = true;
                } else {
                    this.showMenuDesktop = true;
                    this.showMenuMobile = false;
                }
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
    header#AgencyHeader {
        display: flex;
        align-items: center;
    }

    nav#navigation-buttons {
        justify-content: center;

        margin-right: 30px;


    }

</style>