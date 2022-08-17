<script>
export default {
    props: {
        links: {
            type: Array,
        },
    },
};
</script>

<template>
    <div class="bread-crumbs">
        <div class="d-flex align-center">
            <nuxt-link
                v-for="(link, index) in links"
                :key="index"
                :to="link.url"
            >
                {{ link.title }}
                <span v-if="links.length - 1 != index" class="ml-1 mr-1">
                    /
                </span>
            </nuxt-link>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.bread-crumbs {
    display: flex;
    align-items: center;

    a,
    span {
        font-family: "SerifPro-Regular";
        text-decoration: unset;
        font-style: normal;
        font-weight: 400;
        font-size: 12px;
        line-height: 15px;
        letter-spacing: 0.1em;
        color: #035aa6;
    }
}
</style>