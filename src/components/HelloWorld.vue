<template>
  <div class="Helloworld">
    <ul v-for="(list, index) in list" :key="index">
      <li>
        {{ list }} 
        <button @click="eliminar"> Eliminar </button>
      </li>
    </ul>
  </div>
</template>



<script>
export default {
  name: "helloWorld",
  props:{
    list: Array,
  },
  methods: {
    eliminar(index) {
    this.$emit('eliminar', index);
    }
  }

};
</script>
<style scoped>
.li {
  text-align: center;
}
</style>

