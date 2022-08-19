<script>
import breadCrumbs from "../../components/ui/breadCrumbs.vue";
import NavBar from "../../components/ui/navBar.vue";
export default {
    components: { breadCrumbs, NavBar },
    data() {
        return {
            links: [
                {
                    title: "Главная",
                    url: "/",
                },
                {
                    title: "Проекты",
                    url: "/projects",
                },
            ],
            navbar: {
                title: "Наши проекты",
                list: [],
            },
            data: [],
        };
    },
    created() {
        this.getProjectsList();
    },
    methods: {
        async getProjectsList() {
            let params = {};
            params.lang = this.$i18n.locale == "en" ? "en" : "ru" ? "ru" : "kz";
            this.data = (
                await this.$axios.get(`/projects`, { params })
            ).data.data;
            this.data.forEach((e) => {
                let obj = {
                    title: "Наши проекты",
                    title_text: e.title,
                };
                this.navbar.list.push(obj);
            });
        },
    },
};
</script>


<template>
    <main class="projects py">
        <div class="projects__container main-container">
            <bread-crumbs :links="links" />
            <div class="projects__main">
                <nav-bar :navbar="navbar" />
                <div class="projects__description d-flex flex-column">
                    <h3 class="projects__title">Описание о наших проектах</h3>
                    <p class="projects__subtitle">
                        Lorem Ipsum - это текст-"рыба", часто используемый в
                        печати и вэб-дизайне. Lorem Ipsum является стандартной
                        "рыбой" для текстов на латинице с начала XVI века. В то
                        время некий безымянный печатник создал большую коллекцию
                        размеров и форм шрифтов, используя Lorem Ipsum для
                        распечатки образцов. Lorem Ipsum не только успешно
                        пережил без заметных изменений пять веков, но и
                        перешагнул в электронный дизайн.<br />
                        <br />Lorem Ipsum - это текст-"рыба", часто используемый
                        в печати и вэб-дизайне. Lorem Ipsum является стандартной
                        "рыбой" для текстов на латинице с начала XVI века. В то
                        время некий безымянный печатник создал большую коллекцию
                        размеров и форм шрифтов, используя Lorem Ipsum для
                        распечатки образцов. Lorem Ipsum не только успешно
                        пережил без заметных изменений пять веков, но и
                        перешагнул в электронный дизайн. <br />
                        <br />Lorem Ipsum - это текст-"рыба", часто используемый
                        в печати и вэб-дизайне. Lorem Ipsum является стандартной
                        "рыбой" для текстов на латинице с начала XVI века. В то
                        время некий безымянный печатник создал большую коллекцию
                        размеров и форм шрифтов, используя Lorem Ipsum для
                        распечатки образцов. Lorem Ipsum не только успешно
                        пережил без заметных изменений пять веков, но и
                        перешагнул в электронный дизайн.
                    </p>
                </div>
            </div>
        </div>
    </main>
</template>


<style lang="scss" scoped>
.projects {
    &__main {
        margin-top: 55px;

        display: flex;
    }
    &__navbar {
        max-width: 374px;
        width: 100%;
        margin-right: 48px;
        height: 578px;
        overflow-y: scroll;
        border-radius: 3px;
        background: #035aa6;
    }
    &__title {
        font-family: "SerifPro-Semibold";
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #035aa6;
    }
    &__subtitle {
        font-family: "SerifPro-Regular";
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 20px;
        color: #000000;
        margin-top: 25px;
    }
}
</style>