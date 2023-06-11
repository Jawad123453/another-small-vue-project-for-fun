<template>
  <div class="contaner" @click.self="removeitt">
    <div class="tryingthismodel">
      <div class="tryingthismodel-text">
        <slot />
      </div>
      <div class="tryingthismodel-button">
        <slot name="tryingthismodelbutton"></slot>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    methods: {
      removeitt() {
        this.$emit(`close`)
      }
    },
  }
</script>

<style scoped>
.contaner{
  background-color: rgba(221, 221, 221,0.5);
  width:100%;
  height:100vh;
  position: absolute;
  top:0;
  left:0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.tryingthismodel{
  background-color: white;
  padding:20px;
  text-align: center;
  width:300px;
  margin:0 auto;
  display:flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  border-radius: 20px;
}
.tryingthismodel-text h1{
  font-weight: normal;
  color:indianred;
}
.tryingthismodel-text p{
  color:#777;
}
.tryingthismodel-button{
  display: flex;
  align-items: center;
  gap:10px;
}
.tryingthismodel-button button{
  padding:5px 10px;
  background-color: rgb(141, 141, 141);
  color:white;
  cursor: pointer;
  border: none;
  border-radius: 5px;
}
</style>