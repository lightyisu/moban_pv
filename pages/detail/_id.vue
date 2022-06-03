<template>
  <div class="wrapper">
    <div class="content">
      <h2>模板详情</h2>
      <el-card :body-style="{ padding: '40px' }">
          <div  class="title" slot="header">
              <h4>
                        大学生航海王HTML简单网页设计作品海贼王网页制作 4页 带视频
              </h4>
        

          </div>
        <img
          src="https://www.lilixing.com/wp-content/uploads/2022/03/%E7%BD%91%E7%AB%99%E9%A6%96%E9%A1%B5.jpg"
          class="image"
        />
        <div style="padding: 14px">
            <h2>作品介绍</h2>
         <p>
             大学生html简单网页设计作品题材为我喜欢的漫画—航海王（海贼王网页制作）作品共4个页面包括网站首页、故事介绍、主要角色、创作背景。整体排版为LOGO、导航、正文区域，整体使用css设置了网页背景图片，首页插入了视频，有图片列表页面，其他子页面为图文混排。
         </p>
         <h2>作品设计结构</h2>
            <p>
              <el-tag type="info"> DIV </el-tag>
              <el-tag type="info"> CSS </el-tag>
            </p>
             <h2>是否使用JS</h2>
             <p>否</p>
          <div class="bottom clearfix">
            <el-button type="primary" class="button">下载</el-button>
          </div>
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
export default {};
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
.image{
    width: 400px;
}
h4{
    font-size: 20px;
    margin: 0;
    color: black;
    &::before{
        content: '|';
        color: #ffc300;
        font-weight: bold;
    }
}
::v-deep .el-button{
    color: black;
    font-weight: bold;
}


</style>
