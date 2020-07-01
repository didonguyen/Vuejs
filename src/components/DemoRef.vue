<template>
  <div class="demo-ref">
      <button class="avatar" v-on:click="handleClickInputFile">Change Avatar</button>
     <input type="file" style="display:none" ref="fileInputAvatar"> 
  </div>
</template>

<script>
export default {
  name: 'DemoRef',
  data() {
      return {

      }
  },
  methods: {
      handleClickInputFile(e){
          this.$refs.fileInputAvatar.click();
          console.log(this);
      }
  }
};
</script>

<style>
    .demo-ref{
        margin-top: 100px;
        padding: 100px 30px;
        border: solid 2px #333;
    }
    .demo-ref .avatar{
        padding: 12px 15px;
        background-color: #333;
        color: #FFF;
        transition: all .3s ease;
    }
    .avatar:hover {
        background-color: #AAA;
        color:black
    }
</style>
