<template>
  <div class="main-wrapper">
    <MainBar />
    <div class="content-box">
      <div class="content-title hidden-sm-and-down">
        <span>一个快速开发的编程沙盒</span>
        <span>减少您的配置成本</span>
        <span class="title-time">即刻生成</span>
      </div>
      <div class="content-info hidden-sm-and-down">
        <span>项目之间都是独立的，安全，快速得到一个满意的项目原型</span>
      </div>
      <div class="project-wrapper">
        <div class="project-box">
          <span class="project-title">热门语言</span>
          <div class="project-card-list">
            <el-row :gutter="20">
              <el-col
                class="project-card-wrapper"
                :xs="24"
                :lg="5"
                v-for="lang in hotLangList"
                :key="lang.cardName"
              >
                <project-card
                  hot="true"
                  :imgSrc="lang.imgSrc"
                  :cardName="lang.cardName"
                  :cardInfo="lang.cardInfo"
                  @click="clickCard(lang.codeType)"
                />
              </el-col>
            </el-row>
          </div>
        </div>
        <div class="project-box">
          <span class="project-title">可用语言</span>
          <div class="project-card-list">
            <el-row :gutter="20">
              <el-col
                class="project-card-wrapper"
                :xs="24"
                :lg="5"
                v-for="lang in LangList"
                :key="lang.cardName"
              >
                <project-card
                  :imgSrc="lang.imgSrc"
                  :cardName="lang.cardName"
                  :cardInfo="lang.cardInfo"
                  :info="lang.info"
                  @click="clickCard(lang.codeType)"
                />
              </el-col>
            </el-row>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MainBar from "./components/MainBar.vue";
import ProjectCard from "common/ProjectCard.vue";
export default {
  name: "MainPage",
  components: {
    MainBar,
    ProjectCard,
    ProjectCard,
  },
  data: function () {
    return {
      hotLangList: [
        {
          cardName: "Python",
          cardInfo: "解释型语言",
          imgSrc: require("@/assets/lang/python.png"),
          codeType: "PYTHON3",
        },
        {
          cardName: "Java",
          cardInfo: "优秀的跨平台语言",
          imgSrc: require("@/assets/lang/java.png"),
          codeType: "JAVA",
        },
        {
          cardName: "C语言",
          cardInfo: "老而稳定",
          imgSrc: require("@/assets/lang/C.png"),
          codeType: "C",
        },
        {
          cardName: "Golang",
          cardInfo: "简洁、快速",
          imgSrc: require("@/assets/lang/go.png"),
          codeType: "Go",
        },
      ],
      LangList: [
        {
          cardName: "C++",
          cardInfo: "多种编程思想的语言",
          imgSrc: require("@/assets/lang/c++.png"),
          codeType:"CPP"
        },
        {
          cardName: "Python",
          cardInfo: "解释型语言",
          imgSrc: require("@/assets/lang/python.png"),
          codeType: "PYTHON3",
        },
        {
          cardName: "Java",
          cardInfo: "优秀的跨平台语言",
          imgSrc: require("@/assets/lang/java.png"),
          codeType: "JAVA",
        },
        {
          cardName: "C语言",
          cardInfo: "老而稳定",
          imgSrc: require("@/assets/lang/C.png"),
          codeType: "C",
        },
        {
          cardName: "Golang",
          cardInfo: "简洁、快速",
          imgSrc: require("@/assets/lang/go.png"),
          codeType: "Go",
        },
        // {
        //   info: "Beta",
        //   cardName: "Vue",
        //   cardInfo: "渐进式框架",
        //   imgSrc: require("@/assets/lang/vue.png"),
        // },
      ],
    };
  },
  methods: {
    clickCard(codeType) {
      console.log(codeType);
      // this.$router.push("/code");
    },
  },
};
</script>

<style scoped>
.main-wrapper {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(to right bottom, #0d1d3a 0, #1a2f55 52%, #365a83);
  overflow-x: hidden;
  overflow-y: scroll;
}
.content-box {
  /* width: 1200px; */
  margin: 0 auto;
  color: #fff;
  padding-top: 50px;
  width: 65%;
}
.content-title {
  display: flex;
  flex-direction: column;
  font-size: 64px;
}
.content-title > span {
  line-height: 150%;
}

.title-time {
  color: #00e6ff;
}

.content-info {
  margin-top: 5px;
}
.project-wrapper {
  margin-top: 50px;
}

.project-card-wrapper {
  margin-bottom: 15px;
}

.project-box {
  display: flex;
  flex-direction: column;
  margin-bottom: 50px;
  margin-left: 10px;
  margin-right: 10px;
}

.project-card-list {
  /* display: flex; */
  margin-top: 10px;
  /* flex-wrap: wrap; */
  /* width: 1000px; */
  /* row-gap: 20px; */
}

.project-title {
  font-size: 14px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  opacity: 0.9;
}
</style>