<template>
  <div class="estilo">
    <img src="../assets/completo.jpg" v-bind:style="estilo" />
  </div>
</template>

<script>
export default {
  name: "Venta",
  data:function() {
    return {
      //articulo: '../assets/completo.jpg',
      estilo:{
        height: '400px'
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.estilo {
  display: flex;
  justify-content: center;
  width: 80%;
  background-color: yellow;
  border: 1px solid grey;
  border-radius: 30px;
  margin-top: 20px;
}
</style>
