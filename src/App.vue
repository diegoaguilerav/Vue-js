<template>
  <div id="app">
    <div class="navbar">
      <div><input type="checkbox" v-model="bienvenido" /> Bienvenida</div>
      <div><input type="checkbox" v-model="nuestra_propuesta" /> Nuestra propuesta</div>
      <div><input type="checkbox" v-model="lo_que_vendemos" /> Lo que vendemos</div>
      <div><input type="checkbox" v-model="quienes_somos" /> Quiénes somos</div>
      <div><input type="checkbox" v-model="todos" @click="mostrar_todos" /> Todos</div>
    </div>
    <div class="componentes">
      <Bienvenidos v-show="bienvenido"/>
      <Propuesta v-show="nuestra_propuesta"/>
      <Venta v-show="lo_que_vendemos"/>
      <QuienesSomos v-show="quienes_somos"/>
    </div>
  </div>
</template>

<script>
import Bienvenidos  from "./components/Bienvenidos.vue";
import Propuesta    from "./components/Propuesta.vue";
import Venta        from "./components/Venta.vue";
import QuienesSomos from "./components/QuienesSomos.vue";

export default {
  name: "App",
  components: {
    Bienvenidos,
    Propuesta,
    Venta,
    QuienesSomos,
  },
  data: function () {
    return {
      bienvenido: false,
      nuestra_propuesta: false,
      lo_que_vendemos: false,
      quienes_somos: false,
      todos: false,
    };
  },
  methods: {
    mostrar_todos: function () {
      if (!this.todos) {
        this.bienvenido = true;
        this.nuestra_propuesta = true;
        this.lo_que_vendemos = true;
        this.quienes_somos = true;
      } else {
        this.bienvenido = false;
        this.nuestra_propuesta = false;
        this.lo_que_vendemos = false;
        this.quienes_somos = false;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  background-color: royalblue;
}
.navbar {
  display: flex;
  justify-content: space-evenly;
  background-color: cornflowerblue;
  border: 2px solid black;
  border-left: 2px dashed black;
  border-right: 2px dashed black;
  border-radius: 30px;
  padding: 10px 0;
}
.componentes {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
