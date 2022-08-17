<script>
export default {
    data() {
        return {
            swiperOptions2: {
                slidesPerView: 3,
                loop: false,
                spaceBetween: 15,
                watchOverflow: true,
                speed: 500,
                transition: 5000,
                direction: "horizontal",

                navigation: {
                    nextEl: ".swiper-button-next",
                    prevEl: ".swiper-button-prev",
                },
            },
            news: [
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    created_at: "20/08/2021",
                    views: 20,
                    img: require("@/assets/images/Home/news/news_img1.png"),
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    created_at: "20/08/2021",
                    views: 20,
                    img: require("@/assets/images/Home/news/news_img2.png"),
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    created_at: "20/08/2021",
                    views: 20,
                    img: require("@/assets/images/Home/news/news_img3.png"),
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    created_at: "20/08/2021",
                    views: 20,
                    img: require("@/assets/images/Home/news/news_img2.png"),
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    created_at: "20/08/2021",
                    views: 20,
                    img: require("@/assets/images/Home/news/news_img3.png"),
                },
            ],
        };
    },
};
</script>

<template>
    <div class="news">
        <div class="news__content main-container">
            <div class="news__main">
                <h3>Новости</h3>
                <p>
                    В настоящее время ведутся работы по Программе Европейского
                    Банка Реконструкции и развития на территории Кыргызской
                    Республики на объекте «Водный субпроект города Баткен».
                </p>
                <button>Читать больше</button>
            </div>
            <client-only>
                <swiper ref="swiper2" class="swiper2" :options="swiperOptions2">
                    <swiper-slide
                        v-for="(item, index) in news"
                        :key="index"
                        class="swiper-slide"
                    >
                        <img :src="item.img" />
                        <div class="news__details">
                            <div class="d-flex align-center">
                                <svg width="16" height="16">
                                    <use
                                        href="@/assets/images/icons.svg#news-created-at"
                                    ></use>
                                </svg>
                                <span>{{ item.created_at }}</span>
                            </div>
                            <div class="d-flex align-center">
                                <svg width="16" height="16">
                                    <use
                                        href="@/assets/images/icons.svg#news-views"
                                    ></use>
                                </svg>
                                <span>
                                    {{ item.views }}
                                </span>
                            </div>
                        </div>
                        <h5>
                            {{ item.title }}
                        </h5>
                        <p>{{ item.content }}</p>
                    </swiper-slide>
                    <!-- <div class="swiper-button-prev swiper-prev"></div>
                    <div class="swiper-button-next swiper-next"></div> -->
                </swiper>
            </client-only>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.news {
    background: #f9f9f9;
    padding: 64px 0;
    &__content {
        display: flex;
    }
    &__main {
        max-width: 342px;
        width: 100%;
        display: flex;
        flex-direction: column;

        margin-right: 38px;

        h3 {
            font-family: "SerifPro-SemiBold";
            font-style: normal;
            font-weight: 600;
            font-size: 28px;
            line-height: 136%;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: #035aa6;
        }
        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 136%;
            color: #2e2e2e;
            margin: 20px 0 12px;
        }
        button {
            width: 180px;
            height: 50px;
            border-radius: 3px;
            border: 1px solid #035aa6;
            padding: 0 30px;
            background: none;

            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 600;
            font-size: 14px;
            line-height: 136%;
            text-align: center;
            text-transform: uppercase;
            color: #035aa6;
        }
    }
    .swiper {
        max-width: 846px;
        width: 100%;

        display: grid;
        grid-template-columns: repeat(auto-fit, 272px);
    }

    .swiper-slide {
        display: flex;
        flex-direction: column;

        img {
            object-fit: cover;
            margin-bottom: 15px;
        }
        h5 {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 18px;
            line-height: 136%;
            color: #2e2e2e;
            margin: 15px 0 10px;
        }
        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 136%;
            color: #2e2e2e;
        }
    }
    &__details {
        display: flex;
        align-items: center;
        justify-content: space-between;

        padding-right: 8px;

        span {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 136.69%;
            color: #828282;
            margin-left: 8px;
        }
    }
}
.swiper-prev,
.swiper-next {
    position: fixed;
    color: #035aa6;
}
.swiper-prev {
    left: 0 !important;
    right: unset !important;
}
.swiper-next {
    right: 0 !important;
    left: unset !important;
}
</style>