<template>
    <div class="CilckMe" v-if="start2" @click="closethatbtn">
      <h1>Cilck Me</h1>
    </div>
  
</template>

<script>
  export default {
  props: {
    start2:Boolean
  },
  methods: {
    closethatbtn() {
      this.$emit(`closeit`)
    }
  },
  }
</script>

<style scoped>
.CilckMe{
  width:400px;
  height:200px;
  background-color: rgb(0, 196, 33);
  display: flex;
  justify-content: center;
  align-items: center;
  margin:10px auto;
  color:white;
  border:none;
  cursor: pointer;
  border-radius: 10px;
}
</style>