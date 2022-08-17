<script>
import Swiper, { Navigation, Pagination, Autoplay } from "swiper";
Swiper.use([, Navigation, Pagination, Autoplay]);
export default {
    data() {
        return {
            activeIndex: 0,
            swiperOptions: {
                slidesPerView: 1,
                loop: false,
                spaceBetween: 20,
                watchOverflow: true,
                speed: 500,
                transition: 5000,
                direction: "horizontal",

                navigation: {
                    nextEl: ".swiper-button-next",
                    prevEl: ".swiper-button-prev",
                },
            },
            content: [
                {
                    title: "Agidel-as Компания по водоснабжению",
                    btn_text: "оставить заявку",
                    bg_image: require("@/assets/images/Home/swiper-image.png"),
                },
                {
                    title: "Наша компания обладает лицензией 1 категории",
                    btn_text: "Посмотреть лицензию",
                    bg_image: require("@/assets/images/Home/swiper-image2.png"),
                },
            ],
        };
    },
    methods: {
        onSlideChange() {
            this.activeIndex = this.$refs.swiper.$swiper.activeIndex;
        },
    },
};
</script>
<template>
    <div class="intro">
        <client-only>
            <swiper
                ref="swiper"
                :options="swiperOptions"
                class="swiper"
                @slideChange="onSlideChange"
            >
                <swiper-slide
                    v-for="(item, index) in content"
                    :key="index"
                    class="swiper-slide"
                >
                    <img :src="item.bg_image" class="img" />
                    <div class="swiper-content">
                        <h1 :class="{ long_text: activeIndex == 1 }">
                            {{ item.title }}
                        </h1>
                        <button class="button">
                            {{ item.btn_text }}
                        </button>
                    </div>
                    <div class="swiper-button-prev swiper-prev"></div>
                    <div class="swiper-button-next swiper-next"></div>
                </swiper-slide>
            </swiper>
        </client-only>
    </div>
</template>


<style lang="scss" scoped>
.swiper {
    display: flex;
    height: 700px;
}
.swiper-slide {
    height: 100%;
    position: relative;
    h1 {
        font-family: "SerifPro-Bold";
        font-style: normal;
        font-weight: 700;
        font-size: 40px;
        line-height: 50px;
        letter-spacing: 0.2em;
        text-transform: uppercase;
        color: #ffffff;
        max-width: 600px;
    }
    .long_text {
        max-width: 776px;
    }
    .button {
        width: 189px;
        height: 50px;
        border-radius: 3px;
        font-style: normal;
        font-weight: 700;
        font-size: 14px;
        line-height: 18px;
        text-align: center;
        letter-spacing: 0.04em;
        text-transform: uppercase;
        color: #ffffff;
        background: unset;
        border: 1px solid white;
        margin-top: 30px;
        padding: 0 25px;
    }
}
.swiper-prev,
.swiper-next {
    position: absolute;
    color: white;
    opacity: 0.7;
}
.swiper-next {
    right: 89px;
    left: auto;
}
.swiper-prev {
    left: 89px;
    right: auto;
}
.swiper-content {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    padding-top: 167px;
}
.img {
    z-index: -1;
    position: absolute;
    max-width: 100%;
    width: 100%;
    height: auto;
    top: 0;
    left: 0;
}
</style>