<template>
  <div id="app">
    <div class="container">
      <button v-on:click="title='Learning..'">Change From App.vue</button>
      <comp-header
        v-bind:title="title"
        v-on:changeTitleEvent="handleChangeTitle"
      
      />
      <list-user v-bind:listUser="listUser"
        v-on:deleteUserEvent="handleDeleteUser"
      />
      <comp-footer v-bind:title="title"/>
      <demo-ref />
      <demo-slot />
    </div>
  </div>

</template>
<script>
import CompHeader from './components/CompHeader.vue';
import CompFooter from './components/CompFooter.vue';
import ListUser from './components/ListUser.vue';
import DemoRef from './components/DemoRef.vue';
import DemoSlot from './components/DemoSlot.vue';

export default {
  name: 'app',
  data () {
    return {
      title: 'Title From App.vue',
      listUser: [
        { id:100, email: 'test1@gmail.com', isActive: true},
        { id:101, email: 'test2@gmail.com', isActive: false},
        { id:102, email: 'test3@gmail.com', isActive: true},
        { id:103, email: 'test4@gmail.com', isActive: true},
        { id:104, email: 'test5@gmail.com', isActive: false},
      ]
    }
  },
  components: {
    CompHeader,
    CompFooter,
    ListUser,
    DemoRef,
    DemoSlot

  },
  methods: {
    handleChangeTitle(data){
      this.title = data.title;
    },
    handleDeleteUser(data){
      var indexDelete = -1;
      this.listUser.forEach((u, idx) => {
        if(u.id === data.id){
          indexDelete = idx;
          // console.log('Index:', idx);
          this.listUser.splice(idx, 1);
        }
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  max-width: 1170px;
  margin: 0 auto;
  padding: 0 15px;
  min-height: 3000px;
}
</style>
