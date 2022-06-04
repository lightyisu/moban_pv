<template>
  <div class="footer">
      <img width="150px" src='~/assets/box.png'/>
    <div>
        &copy;2022
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.footer{
    height: 150px;
    display: flex;
    align-content: center;
    align-items: center;
    background: #fff;
    padding:0 40px;
}
img{
    object-fit: contain;

}
div{
    height: fit-content;
    display: inline-block;
    font-weight: bold;
    margin-left: 10px;
    vertical-align: middle;
}
</style>