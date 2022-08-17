<script>
import breadCrumbs from "../../components/ui/breadCrumbs.vue";
export default {
    components: { breadCrumbs },
    data() {
        return {
            links: [
                {
                    title: "Главная",
                    url: "/",
                },
                {
                    title: "Контакты",
                    url: "/contacts",
                },
            ],
        };
    },
};
</script>

<template>
    <main class="main-container py contacts">
        <bread-crumbs :links="links" />
        <div class="d-flex mt-14">
            <div class="contacts__details">
                <h1 class="contacts__title">Контакты</h1>
                <a href="tel: +77777777777">
                    <svg width="16" height="16">
                        <use
                            href="@/assets/images/icons.svg#contacts-phone"
                        ></use>
                    </svg>
                    +7 777 777 77 77
                </a>
                <a href="mailto:contact@adigel-as.kz">
                    <svg width="16" height="12">
                        <use
                            href="@/assets/images/icons.svg#contacts-mail"
                        ></use>
                    </svg>
                    contact@adigel-as.kz
                </a>
                <a
                    href="https://yandex.kz/maps/162/almaty/house/Y08YfwdpTEcDQFppfX5yd3hiYA==/?ll=76.909523%2C43.236415&z=16.81"
                >
                    <svg width="16" height="16">
                        <use
                            href="@/assets/images/icons.svg#contacts-location"
                        ></use>
                    </svg>
                    БЦ SAT Business улица Манаса 32А
                </a>
            </div>
            <iframe
                src="https://yandex.kz/map-widget/v1/-/CCURbVXXCC"
                width="560"
                height="400"
                frameborder="1"
                allowfullscreen="true"
                style="position: relative"
            ></iframe>
        </div>
    </main>
</template>


<style lang="scss" scoped>
.contacts {
    &__details {
        display: flex;
        flex-direction: column;

        max-width: 280px;
        width: 100%;
        margin-right: 32px;

        h1 {
            font-family: "SerifPro-Bold";
            font-style: normal;
            font-weight: 400;
            font-size: 28px;
            line-height: 35px;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: #035aa6;
            margin-bottom: 30px;
        }
        a {
            font-family: "SerifPro-Regular";
            text-decoration: unset;
            display: flex;
            align-items: center;
            font-style: normal;
            font-weight: 400;
            font-size: 16px;
            line-height: 136%;
            color: #2e2e2e;
            margin-bottom: 8px;
            &:last-of-type {
                margin-bottom: 0;
            }
        }
        svg {
            margin-right: 5px;
        }
    }
    iframe {
        max-width: 932px;
        width: 100%;
        min-height: 362px;
        border-radius: 5px;
        height: auto;
        border: unset;
    }
}
</style>