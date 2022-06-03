<template>
  <div class="wrapper">
    <div class="content">
      <h2>HTML模板</h2>
      <div class="lists">
        <el-card
          :body-style="{ padding: '0px' }"
          v-for="index in 10"
          :key="index"
        >
          <img
            src="https://www.lilixing.com/wp-content/themes/ceomax/timthumb.php?src=https://www.lilixing.com/wp-content/uploads/2022/03/479ae50a2aaaab4c840002105a5f1de5.png&h=200&w=300&zc=1&a=c&q=100&s=1"
            class="image"
          />
          <div style="padding: 14px">
            <p>航海王HTML简单网页设计作品海贼王网页制作 4页 带视频</p>
            <p>
              <el-tag type="info"> DIV </el-tag>
              <el-tag type="info"> CSS </el-tag>
            </p>

            <div class="bottom clearfix">
              <Nuxt-link to="/detail/312">
                <el-button type="primary" class="button">下载</el-button>
              </Nuxt-link>
            </div>
          </div>
        </el-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
<style lang="scss" scoped>
.wrapper {
  display: flex;
  justify-content: center;
}
.content {
  width: 1000px;
  padding: 20px 0;
}
h2 {
  position: relative;
  z-index: 0;
  display: inline-block;
  &:hover {
    &::after {
      top: 0%;
    }
  }
}
h2::after {
  content: "";
  position: absolute;
  z-index: -1;
  top: 60%;
  left: 0px;
  right: 0px;
  bottom: 0;
  transition: top 200ms cubic-bezier(0, 0.8, 0.13, 1);
  background-color: #ffc300;
}
::v-deep .el-card {
  display: inline-block;
  margin: 15px;
  width: 300px;
  .el-button {
    color: black;
    font-weight: bold;
  }
}
</style>
