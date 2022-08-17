<template>
    <main>
        <intro />
        <services />
        <projects />
        <news />
    </main>
</template>

<script>
import Intro from "../components/home/Intro.vue";
import News from "../components/home/News.vue";
import Projects from "../components/home/Projects.vue";
import Services from "../components/home/Services.vue";
export default {
    components: { Intro, Services, Projects, News },
};
</script>

<style>
</style>