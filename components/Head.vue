<template>
  <div class="head">
      <Nuxt-link to='/'>
          <img width="140px" src="~/assets/logo.png"/>
      </Nuxt-link>
    
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.head{
    height: 80px;
    background: #fff;
    display: flex;
    box-shadow: 0 2px 27px 0 rgb(0 0 0 / 10%);
    align-items: center;
    img{
        object-fit: contain;
        margin-left: 5vw;
    }
}

</style>