<script>
export default {
    data() {
        return {
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
                {
                    title: "Контакты",
                    url: "/contacts",
                },
            ],
            links: [
                {
                    img: require("@/assets/images/Footer/socials/facebook.png"),
                    url: "/",
                },
                {
                    img: require("@/assets/images/Footer/socials/instagram.png"),
                    url: "/",
                },
                {
                    img: require("@/assets/images/Footer/socials/twitter.png"),
                    url: "/",
                },
                {
                    img: require("@/assets/images/Footer/socials/telegram.png"),
                    url: "/",
                },
                {
                    img: require("@/assets/images/Footer/socials/whatsApp.png"),
                    url: "/",
                },
            ],
            contacts: [
                {
                    title: "+7 777 777 77 77",
                    icon: "@/assets/images/icons.svg#footer-phone.svg",
                },
                {
                    title: "contact@adigel-as.kz",
                    icon: "@/assets/images/icons.svg#footer-mail.svg",
                },
                {
                    title: "БЦ SAT Business улица Манаса 32А",
                    icon: "@/assets/images/icons.svg#footer-location.svg",
                },
            ],
        };
    },
};
</script>


<template>
    <div class="footer">
        <div class="footer__container main-container">
            <div class="footer__rules">
                <nuxt-link to="/" class="d-flex align-center">
                    <img
                        src="@/assets/images/Footer/Logo.png"
                        class="footer__logo"
                    />
                </nuxt-link>
                <nuxt-link to="/license" class="mt-5 mb-9"
                    >Лицензия СМР I категория ТОО Агидель-Ас (1)
                </nuxt-link>
                <nuxt-link to="/terms">Пользовательское соглашение </nuxt-link>
                <nuxt-link to="/policy" class="mt-1 mb-3"
                    >Политика конфиденциальности
                </nuxt-link>
                <p class="footer__rights">© 2022 «AGIDEL-AS»</p>
            </div>
            <div class="footer__navigation nav">
                <nuxt-link
                    class="nav__link"
                    v-for="(item, index) in nav"
                    :key="'A' + index"
                    :to="item.url"
                >
                    {{ item.title }}
                </nuxt-link>
            </div>
            <div class="footer__links">
                <div class="footer__socials">
                    <img
                        v-for="(img, idx) in links"
                        :key="'B' + idx"
                        :src="img.img"
                    />
                </div>
                <div class="footer__contacts">
                    <div>
                        <svg width="16" height="16">
                            <use
                                href="@/assets/images/icons.svg#footer-phone"
                            ></use>
                        </svg>
                        <a href="tel: +77777777777">+7 777 777 77 77</a>
                    </div>
                    <div>
                        <svg width="16" height="12">
                            <use
                                href="@/assets/images/icons.svg#footer-mail"
                            ></use>
                        </svg>
                        <a href="mailto: contact@adigel-as.kz"
                            >contact@adigel-as.kz</a
                        >
                    </div>
                    <div>
                        <svg width="20" height="20">
                            <use
                                href="@/assets/images/icons.svg#footer-location"
                            ></use>
                        </svg>
                        <a
                            href="https://yandex.kz/maps/162/almaty/house/Y08YfwdpTEcDQFppfX5yd3hiYA==/?ll=76.909523%2C43.236415&z=16.81"
                            >БЦ SAT Business улица Манаса 32А</a
                        >
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.footer {
    background: #083156;
    padding: 60px 0;
    &__container {
        display: flex;
        justify-content: space-between;
        align-items: flex-start !important;
    }
    &__rules {
        display: flex;
        flex-direction: column;

        max-width: 222px;
        width: 100%;
        a {
            text-decoration: unset;
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 18px;
            color: #ffffff;
            cursor: pointer;
        }
        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 136%;
            color: #ffffff;
        }
    }
    &__logo {
        width: 120px;
        height: 114px;
        object-fit: cover;
    }
    &__links {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-end;
    }
    &__socials {
        display: flex;
        align-items: center;

        img {
            object-fit: cover;
            margin-right: 10px;
            &:last-of-type {
                margin-right: 0;
            }
        }
    }
    &__contacts {
        margin-top: 170px;
        div {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            margin-bottom: 5px;
            &:last-of-type {
                margin-bottom: 0;
            }

            a {
                margin-left: 8px;
                font-family: "SerifPro-Regular";
                text-decoration: unset;
                font-style: normal;
                font-weight: 400;
                font-size: 16px;
                line-height: 136%;
                color: #ffffff;
            }
        }
    }
}
</style>