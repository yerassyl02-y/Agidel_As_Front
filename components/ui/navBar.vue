<script>
export default {
    props: {
        navbar: {
            type: Object,
        },
    },
    data() {
        return {
            type: "",
        };
    },
    created() {
        if (process.client) this.type = localStorage.getItem("type");
    },
    methods: {
        goToInner(item) {
            this.$router.push({
                path: `/${this.type}/${item.id}`,
            });
        },
    },
};
</script>

<template>
    <div class="navbar">
        <h3 class="navbar__title">
            {{ navbar.title }}
        </h3>
        <div class="navbar__list">
            <div
                v-for="(item, index) in navbar.list"
                :key="index"
                class="navbar__item"
                @click="goToInner(item)"
            >
                <h4 v-html="item.title_text">{{ item.title_text }}</h4>
                <div v-if="item.details" class="item-details">
                    <div class="d-flex align-center">
                        <svg width="14" height="14" class="mr-2">
                            <use
                                href="@/assets/images/icons.svg#news-id-created-at"
                            ></use>
                        </svg>
                        <span>
                            {{ item.created_at }}
                        </span>
                    </div>
                    <div class="d-flex align-center">
                        <svg width="16" height="16" class="mr-2">
                            <use
                                href="@/assets/images/icons.svg#news-id-views"
                            ></use>
                        </svg>
                        <span>
                            {{ item.views }}
                        </span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.navbar {
    max-width: 374px;
    width: 100%;
    height: 775px;
    overflow-y: scroll;
    padding: 46px 0;
    border-radius: 3px;
    background: #035aa6;

    display: flex;
    flex-direction: column;

    margin-right: 48px;

    &__title {
        font-family: "SerifPro-Semibold";
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #ffffff;
        margin-left: 20px;
    }
    &__list {
        display: flex;
        flex-direction: column;
        margin-top: 30px;
    }
    &__item {
        display: flex;
        flex-direction: column;

        padding: 14px 0 14px 20px;
        transition: 0.33s;
        cursor: pointer;

        h4 {
            max-width: 300px;
            width: 100%;
            word-wrap: break-word;
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 700;
            font-size: 16px;
            line-height: 20px;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            color: #ffffff;
        }
        &:hover {
            background: #31daff;
        }
    }
    .item-details {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding-right: 9px;

        span {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 136.69%;
            color: #ffffff;
        }
    }
}
</style>