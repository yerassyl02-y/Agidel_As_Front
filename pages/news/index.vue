<script>
import breadCrumbs from "../../components/ui/breadCrumbs.vue";
export default {
    components: { breadCrumbs },
    data() {
        return {
            pagination: 8,
            page: 1,
            links: [
                {
                    title: "Главная",
                    url: "/",
                },
                {
                    title: "Новости",
                    url: "/news",
                },
            ],
            data: [],
            news: [
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 1,
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 2,
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 3,
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 4,
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 5,
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 6,
                },
                {
                    title: "Lorem Ipsum - это текст-'рыба'",
                    created_at: "20/08/2021",
                    views: 20,
                    content:
                        "Lorem Ipsum - это текст-'рыба', часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной 'рыбой' для текстов на латинице с начала XVI века.",
                    img: require("@/assets/images/News/news_img.png"),
                    id: 7,
                },
            ],
        };
    },
    methods: {
        async getNewsList() {
            // this.data =
        },
        goToInner(item) {
            this.$router.push({
                path: `/news/${item.id}`,
            });
            if (process.client) {
                localStorage.setItem("news-detail", JSON.stringify(item));
                localStorage.setItem("type", "news");
            }
        },
    },
};
</script>

<template>
    <div class="news py">
        <div class="news__container main-container">
            <bread-crumbs :links="links" />
            <h1 class="news__title">Новости</h1>
            <p class="news__subtitle">
                В настоящее время ведутся работы по Программе Европейского Банка
                Реконструкции и развития на территории Кыргызской Республики на
                объекте «Водный субпроект города Баткен».
            </p>
            <div class="news__list list">
                <div
                    v-for="(item, index) in news"
                    :key="index"
                    class="list__item"
                    @click="goToInner(item)"
                >
                    <img :src="item.img" />
                    <div class="list__details">
                        <div class="d-flex align-center">
                            <svg width="16" height="16" class="mr-2">
                                <use
                                    href="@/assets/images/icons.svg#news-created-at"
                                ></use>
                            </svg>
                            <span>
                                {{ item.created_at }}
                            </span>
                        </div>
                        <div class="d-flex align-center">
                            <svg width="16" height="16" class="mr-2">
                                <use
                                    href="@/assets/images/icons.svg#news-views"
                                ></use>
                            </svg>
                            <span>
                                {{ item.views }}
                            </span>
                        </div>
                    </div>
                    <h5 class="list__title">
                        {{ item.title }}
                    </h5>
                    <p class="list__content">{{ item.content }}</p>
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.news {
    &__container {
        display: flex;
        flex-direction: column;
    }
    &__title {
        font-family: "SerifPro-Bold";
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 136%;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #035aa6;
        margin-top: 44px;
    }
    &__subtitle {
        font-family: "SerifPro-Regular";
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 136%;
        color: #2e2e2e;
        margin: 20px 0;
        max-width: 760px;
        width: 100%;
    }
    &__list {
        display: grid;
        grid-template-columns: repeat(auto-fit, 272px);
        grid-gap: 32px 16px;
    }
}
.list {
    &__item {
        display: flex;
        flex-direction: column;

        cursor: pointer;

        max-width: 272px;
        width: 100%;

        img {
            width: 100%;
            max-height: 168px;
            height: auto;
            object-fit: cover;
            border-radius: 4px;
        }
    }
    &__details {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding-right: 9px;

        margin: 15px 0;

        span {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 136.69%;
            color: #828282;
        }
    }
    &__title {
        font-family: "SerifPro-Semibold";
        font-style: normal;
        font-weight: 400;
        font-size: 18px;
        line-height: 136%;
        color: #2e2e2e;
        margin-bottom: 10px;
    }
    &__subtitle {
        font-family: "SerifPro-Regular";
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 136%;
        color: #2e2e2e;
    }
}
</style>