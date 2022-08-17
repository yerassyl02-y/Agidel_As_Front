<script>
export default {
    data() {
        return {
            swiperOptions3: {
                slidesPerView: 5,
                autoplay: true,
                loop: false,
                spaceBetween: 20,
                watchOverflow: true,
                speed: 500,
                transition: 5000,
                direction: "horizontal",
            },
        };
    },
};
</script>

<template>
    <div class="partners main-container">
        <h4>Наши партнеры</h4>
        <client-only>
            <swiper ref="swiper" class="swiper3" :options="swiperOptions3">
                <swiper-slide
                    class="swiper-slide"
                    v-for="item in 7"
                    :key="item"
                >
                    <img src="@/assets/images/Home/partners.png" />
                </swiper-slide>
            </swiper>
        </client-only>
    </div>
</template>


<style lang="scss" scoped>
.partners {
    display: flex;
    flex-direction: column;

    padding: 100px 0;

    h4 {
        font-family: "SerifPro-Bold";
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #035aa6;
        margin-bottom: 30px;
    }
}
.swiper3 {
    display: grid;
    width: 100%;
    grid-template-columns: repeat(auto-fit, 215px);
}
.swiper-slide {
    display: flex;
    align-items: center;
    justify-content: center;
    background: white;
    border-radius: 5px;
    padding: 10px 15px;
    width: 100%;
    box-shadow: 0px 4px 14px rgba(30, 95, 175, 0.15);
    img {
        width: 90px;
        height: 70px;
        object-fit: cover;
        cursor: pointer;
    }
}
.swiper-wrapper {
    width: 100%;
}
</style>