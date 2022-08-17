<script>
export default {
    data() {
        return {
            projects: [
                {
                    title: "Строительство сетей водоснабжения д/о «Мерекелик» г. Талдыкорган",
                },
                {
                    title: "Энергоснабжение «Gate City» города-спутника в Алматинской области. Тепловые сети.",
                },
                {
                    title: "Строительство сетей водопровода и канализации мкр. Кок-Кайнар (садоводческое общество «Радуга») г. Алматы",
                },
                {
                    title: "Строительство систем водоснабжения и канализации микрорайона «Кокшокы» Бостандыкского района г. Алматы",
                },
                {
                    title: "Водоснабжение и водоотведение Gate City города-спутника в Алматинской области.",
                },
            ],
            active_project: {
                title: "",
            },
        };
    },
    created() {
        this.active_project.title = this.projects[0].title;
    },
    methods: {
        setActiveItem(item) {
            this.active_project.title = item.title;
        },
    },
};
</script>

<template>
    <div class="projects">
        <div class="projects__list">
            <h4>Наши проекты</h4>
            <div class="projects__items">
                <div
                    class="projects__item"
                    v-for="(project, index) in projects"
                    :key="index"
                    @click="setActiveItem(project)"
                >
                    <p>{{ project.title }}</p>
                </div>
            </div>
        </div>
        <div class="projects__active">
            <h5>
                {{ active_project.title }}
            </h5>
            <p>
                Lorem Ipsum — это просто текст-пустышка полиграфической и
                наборной индустрии. Lorem Ipsum был стандартным фиктивным
                текстом в отрасли с 1500-х годов, когда неизвестный печатник
                взял гранку шрифта и перемешал ее, чтобы сделать книгу образцов
                шрифтов.
            </p>
            <button>Подробнее о проекте</button>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.projects {
    display: flex;
    align-items: center;
    padding: 60px 0 160px;

    &__list {
        z-index: 99;
        margin-right: -124px;
        background: #035aa6;
        box-shadow: 4px 4px 24px rgba(0, 0, 0, 0.15);

        padding: 51px 0 80px 95px;

        h4 {
            font-family: "SerifPro-SemiBold";
            font-style: normal;
            font-weight: 600;
            font-size: 28px;
            line-height: 35px;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: #ffffff;
            margin-bottom: 35px;
        }
    }
    &__items {
        display: flex;
        flex-direction: column;
    }
    &__item {
        padding-right: 50px;
        padding-top: 10px;
        cursor: pointer;
        transition: 0.33s;
        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 600;
            font-size: 18px;
            line-height: 136%;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: #ffffff;
        }
        &:hover {
            background: #31daff;
        }
    }
    &__active {
        max-width: 833px;
        width: 100%;
        height: 700px;
        background: url("@/assets/images/Home/projects/bg_image.png");
        background-repeat: no-repeat;
        background-size: cover;

        padding: 148px 0 252px 167px;
        h5 {
            font-family: "SerifPro-SemiBold";
            font-style: normal;
            font-weight: 600;
            font-size: 18px;
            line-height: 136%;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: #ffffff;
        }
        p {
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 400;
            font-size: 18px;
            line-height: 136%;
            color: #ffffff;
            margin: 20px 0 25px;
        }
        button {
            width: 250px;
            height: 50px;
            border-radius: 3px;
            border: 1px solid white;
            background: none;
            padding: 0 30px;
            font-family: "SerifPro-Regular";
            font-style: normal;
            font-weight: 600;
            font-size: 14px;
            line-height: 136%;
            text-align: center;
            text-transform: uppercase;
            color: #ffffff;
        }
    }
}
</style>