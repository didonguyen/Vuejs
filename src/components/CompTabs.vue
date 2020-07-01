<template>
  <div class="comp-tabs">
      <div class="tabs-title">
          <span>{{ title }}</span>
          <ion-icon name="desktop-outline"></ion-icon>
      </div>
      <div class="tabs-content">
          <slot> </slot>
      </div>
  </div>
</template>

<script>
export default {
  name: 'CompTabs',
  props: {
      title: String
  },
  data() {
      return {

      }
  }
};
</script>

<style>
    .tabs-title{
        border: solid 2px #000;
        padding: 15px 30px;
        display: flex;
        justify-content: space-between;
    }
    .tabs-header{
        list-style-type: none;
        margin: 0;
        padding: 0;
        display: flex;
    }
    .tabs-content{
        margin-top: 2px;
        padding: 2px;
        border: 2px solid rgb(29, 107, 209);
    }
    .tabs-header li{
        padding: 8px 15px;
        background-color: #333;
        color: #fff;
        transition: all .3s ease;
    }
    .tabs-header li:hover{
        color:#000;
        background-color: #DDD;
    }
    .tab-content{
        border: 2px solid green;
        margin-top: 2px;
        padding: 2px;
        text-align: left;
    }
    .tabs-header .active{
        color:#000;
        background-color: #DDD;
    }
</style>
