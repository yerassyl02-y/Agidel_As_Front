<script>
export default {
    data() {
        return {
            activeIndex: null,
            nav: [
                {
                    title: "наши услуги",
                    url: `/services`,
                },
                {
                    title: "наши проекты",
                    url: "/projects",
                },
                {
                    title: "новости",
                    url: "/news",
                },
                {
                    title: "О компании",
                    url: "/about",
                },
            ],
        };
    },
};
</script>


<template>
    <div class="header">
        <div class="header__container main-container">
            <nuxt-link to="/" class="header__logo">
                <img src="@/assets/images/Header/Logo.png" />
            </nuxt-link>
            <nav class="header__navigation nav">
                <nuxt-link
                    v-for="(item, index) in nav"
                    :key="index"
                    :to="item.url"
                >
                    {{ item.title }}
                </nuxt-link>
            </nav>
            <div class="header__contacts contacts">
                <svg width="13" height="13">
                    <use href="@/assets/images/icons.svg#header-search"></use>
                </svg>
                <svg width="13" height="13" class="contacts__icon">
                    <use href="@/assets/images/icons.svg#header-phone"></use>
                </svg>
                <img
                    src="@/assets/images/Header/language-russia.png"
                    class="contacts__language"
                />
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.active {
    color: red !important;
}
.header {
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.05);
    padding: 7px 0;
    &__container {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    &__logo {
        display: flex;
        align-items: center;

        cursor: pointer;

        img {
            object-fit: cover;
        }
    }
}
.contacts {
    display: flex;
    align-items: center;
    svg,
    img {
        cursor: pointer;
    }
    &__icon {
        margin: 0 10px;
    }
}
</style>