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
                    title: "О Компании",
                    url: "/about",
                },
            ],
        };
    },
};
</script>


<template>
    <main class="about main-container py d-flex flex-column">
        <bread-crumbs :links="links" />
        <h1>О компании</h1>
        <div class="about__content d-flex">
            <div class="about__text d-flex flex-column">
                <div class="text-items">
                    <h5>о нас</h5>
                    <p>
                        ТОО «АГИДЕЛЬ-АС» является динамично развивающейся
                        компанией, работающей в консорциуме с крупной
                        строительной компанией «Элитстрой». Одним из совместных
                        проектов является строительство Атлетической деревни в
                        г. Алматы.
                    </p>
                </div>
                <div class="text-items">
                    <h5>ПРОИЗВОДСТВЕННАЯ БАЗА</h5>
                    <p>
                        Компания располагает производственной базой и
                        необходимой техникой для качественного и своевременного
                        выполнения строительно-монтажных работ.<br /><br />
                        Штат укомплектован высококвалифицированными
                        специалистами.
                    </p>
                </div>
            </div>
            <div class="about__images">
                <img
                    v-for="img in 8"
                    :key="'A' + img"
                    src="@/assets/images/About/images.png"
                />
            </div>
        </div>
        <div class="about__staff d-flex flex-column">
            <h1 class="staff-title">Команда квалифицированных специалистов</h1>
            <div class="staff-list">
                <div v-for="item in 6" :key="'B' + item">
                    <img src="@/assets/images/About/staff.png" />
                    <p>
                        Фамилия<br />
                        Имя
                    </p>
                    <span>Должность</span>
                </div>
            </div>
        </div>
    </main>
</template>


<style lang="scss" scoped>
.about {
    h1 {
        font-family: "SerifPro-Bold";
        font-style: normal;
        font-weight: 400;
        font-size: 28px;
        line-height: 35px;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #035aa6;
        margin-top: 55px;
    }
    &__content {
        margin: 35px 0 92px;
    }
    &__text {
        max-width: 407px;
        width: 100%;
        margin-right: 13px;
    }
    .text-items {
        display: flex;
        flex-direction: column;

        margin-bottom: 66px;

        h5 {
            font-family: "SerifPro-Semibold";
            font-style: normal;
            font-weight: 600;
            font-size: 16px;
            line-height: 20px;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            color: #2e2e2e;
        }
        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 16px;
            line-height: 20px;
            color: #2e2e2e;
            margin-top: 10px;
        }
        &:last-of-type {
            margin-bottom: 0;
        }
    }
    &__images {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(auto-fit, 200px);
        grid-gap: 35px 10px;

        img {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 5px;
        }
    }
    .staff-title {
        font-family: "SerifPro-Semibold";
        font-style: normal;
        font-weight: 600;
        font-size: 16px;
        line-height: 20px;
        letter-spacing: 0.2em;
        text-transform: uppercase;
        color: #2e2e2e;
    }
    .staff-list {
        display: flex;
        flex-wrap: wrap;

        margin-top: 35px;

        div {
            display: flex;
            flex-direction: column;
            border-radius: 3px;

            max-width: 196px;
            width: 100%;

            background: #ffffff;
            box-shadow: 12px 4px 24px rgba(0, 0, 0, 0.15);

            padding-bottom: 44px;

            margin-right: 25px;
            margin-bottom: 15px;

            img {
                width: 196px;
                height: 182px;
                object-fit: cover;
            }
            p {
                font-family: "SerifPro-Semibold";
                font-style: normal;
                font-weight: 600;
                font-size: 16px;
                line-height: 20px;
                letter-spacing: 0.2em;
                color: #2e2e2e;
                margin: 10px 0 7px;
                margin-left: 11px;
            }
            span {
                margin-left: 11px;
                font-family: "SerifPro-Regular";
                font-style: normal;
                font-weight: 600;
                font-size: 12px;
                line-height: 15px;
                letter-spacing: 0.2em;
                color: #4f4f4f;
            }
            &:last-of-type {
                margin-right: 0;
            }
        }
    }
}
</style>