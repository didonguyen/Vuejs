<template>
  <div class="user">
      {{ user.email }}
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
  }
};
</script>

<style>
</style>
