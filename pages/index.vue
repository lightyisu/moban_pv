<template>
  <div class="wrapper">
    <div class="content">
      <h2>HTML模板</h2>
      <div class="lists">
        <el-card
          :body-style="{ padding: '0px' }"
          v-for="(item,index) in res.data"
          :key="index"
        >
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
export default {
 async asyncData(){
  
       let {data:res}=await axios.get('https://asop2rq5.directus.app/items/moban');
    return{
        res
      }
   
 
 }
};
</script>
<style lang="scss" scoped>
.image{
  width: 100%;
  max-height: 230px;
 
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
  margin: 15px;
  width: 300px;
  
  .el-button {
    color: black;
    font-weight: bold;
  }
}
</style>
