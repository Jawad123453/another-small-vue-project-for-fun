<template>
  <div>
    Hello from new Jawad
    main id = {{ id }}
  </div>
</template>

<script>
  export default {
    data() {
      return {
        id:this.$route.params.id
      }
    },
  }
</script>

<style scoped>

</style>