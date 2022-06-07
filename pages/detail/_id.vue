<template>
  <div class="wrapper">
    <div class="content">
      <h2>制作详情</h2>
   
       
      <el-card :body-style="{ padding: '40px' }">
        <div class="title" slot="header">
          <h4>{{ res.title }}</h4>
        </div>
        <p v-if="res.recommend" style="font-size:24px">
           <i class="el-icon-circle-check" style="color:green;font-size: 24px;"></i>
        推荐作品(高质量作品)
        </p>
            
        <h2>预览(点击查看大图)</h2>
        <p>
          <el-image
            v-for="item in res.img"
            :key="item"
            style="height: 100%"
            :src="item"
            class="image"
            lazy
            :preview-src-list="[item]"
          >
          </el-image>
        </p>

        <div style="padding: 14px">
          <h2>作品介绍</h2>
          <p>
            {{ res.desc }}
          </p>
          <h2>作品设计结构</h2>
          <p>
            <el-tag type="info"> DIV </el-tag>
            <el-tag type="info"> CSS </el-tag>
          </p>
          <h2>是否使用JS</h2>
          <p>否</p>
          <div class="bottom clearfix">
            <el-popover
              placement="bottom"
              title="闲鱼咨询复制以下口令"
              width="200"
              trigger="click"
              content="【闲鱼】https://m.tb.cn/h.ftlkCNU?tk=BAqO2OxvO3Q「我在闲鱼发布了【网页设计模板】」
点击链接直接打开"
            >
              <el-button type="primary" class="button" slot="reference"
                >下载</el-button
              >
            </el-popover>
            <a href="https://m.tb.cn/h.ftlkCNU?tk=BAqO2OxvO3Q" target="_blank">
              <el-button type="primary" class="button" slot="reference"
                >去闲鱼咨询</el-button
              >
            </a>
           
         
          </div>
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  async asyncData({ params }) {
    let { data } = await axios.get(
      "https://asop2rq5.directus.app/items/moban/" + params.id
    );
    let res = data.data;
    return {
      res,
    };
  },
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
  @media screen and (max-width: 800px) {
    & {
      width: 90vw;
    }
  }
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
.image {
  width: 40%;
  padding: 5px;
    @media screen and (max-width: 800px) {
    & {
      width: 90%;
    }
  }
}
h4 {
  font-size: 20px;
  margin: 0;
  color: black;
  &::before {
    content: "| ";
    color: #ffc300;
    font-weight: bold;
  }
}
::v-deep .el-button {
  color: black;
  font-weight: bold;
}
.button{
  margin: 10px 0;
}
</style>
