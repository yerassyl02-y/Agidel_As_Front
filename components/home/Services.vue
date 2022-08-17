
<script>
export default {
    data() {
        return {
            services: [
                {
                    title: "Устройство инженерных сетей и систем",
                    img: require("@/assets/images/Home/services/filter.png"),
                },
                {
                    title: "Строительство автомобильных и железных дорог",
                    img: require("@/assets/images/Home/services/road.png"),
                },
                {
                    title: "Монтаж технологического оборудования,пусконаладочные работы",
                    img: require("@/assets/images/Home/services/toolkit.png"),
                },
                {
                    title: "Специальные работы в грунтах",
                    img: require("@/assets/images/Home/services/excavator.png"),
                },
                {
                    title: "Возведение несущих и ограждающих конструкций ",
                    img: require("@/assets/images/Home/services/construction.png"),
                },
                {
                    title: "Специальные строительные и монтажные работы ",
                    img: require("@/assets/images/Home/services/concrete-mixer.png"),
                },
            ],
        };
    },
};
</script>


<template>
    <div class="main-container services">
        <h3 class="services__title">Наши услуги</h3>
        <div class="services__items">
            <div
                class="services__item"
                v-for="(item, index) in services"
                :key="index"
            >
                <img :src="item.img" />
                <p :class="{ blue_text: index % 2 != 0 }">
                    {{ item.title }}
                </p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.services {
    display: flex;
    flex-direction: column;

    padding: 100px 0;

    &__title {
        font-family: "SerifPro-Semibold";
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #035aa6;
        margin-bottom: 27px;
    }
    &__items {
        display: grid;
        grid-template-columns: repeat(auto-fit, 412px);
    }
    &__item {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: white;
        box-shadow: 12px 4px 24px rgba(0, 0, 0, 0.15);

        padding: 58px 61px 68px 53px;

        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 700;
            font-size: 16px;
            line-height: 20px;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            color: #ffffff;
            margin-top: 40px;
            max-width: 373px;
        }
        .blue_text {
            color: #035aa6;
        }
        img {
            width: 106px;
            height: 106px;
            object-fit: cover;
        }
        &:nth-child(odd) {
            background: #035aa6;
        }
    }
}
</style>