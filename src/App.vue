<template>
  <div id="app">
    <form>
      <p>
        <label for="">Tarea</label>
        <input v-model="respuesta" placeholder="ingresa nueva tarea" />
        <button @click.prevent="btn">Añade</button>
      </p>
    </form>

    <hello-world :list="this.tareas" @eliminar="eliminar"> </hello-world>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: { HelloWorld },
  
  data() {
    return {
      respuesta: "",
      tareas: [],
    };
  },
  methods: {
    btn() {
      this.tareas.push(this.respuesta);
      this.respuesta = "";
    },
    eliminar(index){
      this.tareas.splice(index,1)
    }
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
  padding-right: 0.5rem;
}
</style>
