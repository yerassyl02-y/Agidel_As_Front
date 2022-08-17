<template>
    <v-app>
        <vue-header />
        <Nuxt />
        <vue-footer />
    </v-app>
</template>

<script>
import VueFooter from "../components/ui/vueFooter.vue";
import vueHeader from "../components/ui/vueHeader.vue";
export default {
    components: { vueHeader, VueFooter },
};
</script>

<style>
</style>