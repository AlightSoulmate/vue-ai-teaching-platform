<template>
  <div>
  <nav class="top-nav">
    <TopNav />
  </nav>
  <div class="page-container">
    <!-- 左侧内容区 -->
    <div class="left-section">
      <div class="content-wrapper">
        <div class="big-logo">
          <img :src="logoSrc" ></img>
        </div>
        <div class="title">
          <div class="h1-title">
            <div class="front">{{ h1Title }}</div>
            <div class="end">{{ h1TitleEnd }}</div>
          </div>
        <!-- <h2 class="h2-title">{{ h2Title }}</h2> -->
        </div>
      </div>
    </div>
    <!-- 右侧登录区 -->
    <div class="right-section">
      <div class="login-container">
        <EnterDialog />
      </div>
    </div>
  </div>
  </div>
</template>
<script lang="ts" setup>
import { ref } from "vue";
import TopNav from "@/components/topNav/login/index.vue";
import EnterDialog from "@/components/use/enter.vue";

const h1Title = ref("浙江外国语学院");
const h1TitleEnd = ref("AI智能教学平台");
const h2Title = ref("AI驱动的直观教学反馈与改进，以智能化评估帮助教师和学生完成创新");
const logoSrc = ref("https://a1.x914.com/alight/i/AITeach/loginpage-logo.png");
</script>
<style scoped lang="scss">
* {
  margin: 0;
  padding: 0;
}
.top-nav {
  position: relative;
}
.page-container {
  overflow: hidden;
  color: var(--text-color);
  width: 100%;
  height: 100vh;
  background-color: var(--background-color);
  background-image: linear-gradient(
      0deg,
      transparent 24%,
      var(--color) 25%,
      var(--color) 26%,
      transparent 27%,
      transparent 74%,
      var(--color) 75%,
      var(--color) 76%,
      transparent 77%,
      transparent
    ),
    linear-gradient(
      90deg,
      transparent 24%,
      var(--color) 25%,
      var(--color) 26%,
      transparent 27%,
      transparent 74%,
      var(--color) 75%,
      var(--color) 76%,
      transparent 77%,
      transparent
    );
  background-size: 55px 55px;
  display: flex;
  padding-top: 0;
  position: relative;
}

.left-section {
  flex: 1.3;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10rem 4rem 3rem 4rem;
}

.content-wrapper {
  max-width: 800px;
  transform: translateY(-2rem);
}

.right-section {
  flex: 0.7;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 4rem 3.5rem 0;
  margin-right: 100px;
}

.login-container {
  width: 100%;
  max-width: 380px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
  border-radius: 16px;
  transition: transform 0.3s ease;
  &:hover {
    transform: translateY(-5px);
  }
}
.title {
  overflow: hidden;
  height: 70px;
}
.h1-title{
    display: flex;
  .front {
    font-size: 3.4rem;
    font-weight: 600;
    color: var(--text-color);
    margin-bottom: 1.5rem;
    letter-spacing: -1px;
    animation: fadeInTitle 0.7s ease;
  }
  .end{
    padding-left: 5px;
    font-size: 3.4rem;
    font-weight: 600;
    color: #ff792d;
    margin-bottom: 1.5rem;
    letter-spacing: -1px;
    animation: fadeInTitleEnd 1.1s ease;
  } 
}

.h2-title {
  font-size: 1.4rem;
  color: var(--text-color);
  line-height: 1.6;
  margin-bottom: 2rem;
  opacity: 0.85;
}

.big-logo {
  margin-top: -80px;
  width: 100%;
  height: 380px;
  margin-bottom: 2.5rem;
  // animation: fadeIn 1s ease-out;
  
  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    transition: transform 0.5s ease;
    
    &:hover {
      transform: scale(1.02);
    }
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    // transform: translateY(20px);
  }
  to {
    opacity: 1;
    // transform: translateY(0);
  }
}

@keyframes fadeInTitle {
  from {
    transform: translateY(70px);
  }
  to {
    transform: translateY(0);
  }
}
@keyframes fadeInTitleEnd {
  from {
    transform: translateY(-120px);
  }
  to {
    transform: translateY(0);
  }
}

@media (max-width: 1200px) {
  .left-section {
    padding: 2rem;
  }
  
  .h1-title {
    font-size: 3rem;
  }
}

@media (max-width: 968px) {
  .page-container {
    flex-direction: column;
  }

  .left-section {
    padding: 2rem 1.5rem;
  }

  .right-section {
    width: 100%;
    min-height: auto;
    padding: 2rem 1rem;
  }

  .login-container {
    margin: 0 auto;
  }

  .big-logo {
    height: 300px;
    margin-top: -40px;
  }

  .h1-title {
    font-size: 2.5rem;
    text-align: center;
  }

  .h2-title {
    text-align: center;
  }
}
</style>
