<template>
  <div class="user">
      <h3>{{ user.email }}</h3>
      <button class="delete" v-on:click="handleDelete">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'User',
  props: {
      user: {
          type: Object,
          default: null
      }
  },
  data() {
      return {

      }
  },
  methods: {
      handleDelete(){
          var data = {
              id: this.user.id
          }
        //console.log('user...', data.id);
          this.$emit('deleteUser', data);
      }
  }
};
</script>

<style>
.user .delete{
    position: absolute;
    top: 0;
    right: 0;
}
</style>
