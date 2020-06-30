<template>
  <div>
      <h1>{{ title }} <br>
        <button v-on:click="changeTitleHeader">Change From Header</button>
      </h1>
  </div>
</template>

<script>
export default {
  name: 'CompHeader',
  props: {
      title: String
  },
  data() {
      return {

      }
  },
  methods: {
      changeTitleHeader(){
          var data = {
              title: 'Running From Data Header..'
          }
          this.$emit('changeTitleEvent', data);
      }
  }
};
</script>

<style>
</style>
