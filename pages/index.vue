<template>
  <div class="wrapper">
    <div class="content">
      <h2>HTML制作效果展示</h2>
    
      <div class="lists">
        <el-card
          :body-style="{ padding: '0px' }"
          v-for="(item,index) in res"
          :key="index"
        >
        <div v-if="item.recommend" class="highlight">
        <i class="el-icon-circle-check" style="color:green"></i>
        推荐作品
        </div>

          <el-image
            :src=item.cover
            class="image"
            lazy
          ></el-image>
          <div style="padding: 14px">
            <p>{{item.title}}</p>
            <p>
              <el-tag type="info"> DIV </el-tag>
              <el-tag type="info"> CSS </el-tag>
            </p>

            <div class="bottom clearfix">
              <Nuxt-link :to="'/detail/'+item.id">
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
import axios from "axios";
import reverse from "lodash/reverse"
export default {
 async asyncData(){
  
       let {data:res}=await axios.get('https://asop2rq5.directus.app/items/moban');
       res=reverse(res.data)
    return{
        res
      }
   
 
 }
};
</script>
<style lang="scss" scoped>
.highlight{
  position: absolute;
  width: 100%;
  z-index:100;
  font-weight: bold;
  top: 0;
  left: 0;
  height: 20px;
  background: #ffc609db;
  padding: 10px;
  text-align: center;

}
.image{
  width: 100%;
  max-height: 200px;
 
}
.wrapper {
  display: flex;
  justify-content: center;
}
.content {
  width: 1000px;
  padding: 20px 0;
     @media screen and (max-width: 800px) {
    & {
      width: 90%;
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
::v-deep .el-card {
  display: inline-block;
  position: relative;
  margin: 15px;
  width: 300px;
  
  .el-button {
    color: black;
    font-weight: bold;
  }
}
</style>
