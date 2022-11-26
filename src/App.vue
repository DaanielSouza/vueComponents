<template>
  <!-- <local-component :title="title" @addClick="count++"></local-component> -->
  <local-component :title="title" @addClick="count  += $event">
  <!-- Slot Test -->
  <template v-slot:header>
    Slot Header
  </template>
  <template v-slot:content>
    Slot Content
  </template>
  </local-component>
  <global-component></global-component>
  <p>{{  count  }}</p>
</template>

<script>
import LocalComponent from './components/LocalComponent.vue';
export default {
  data() {
    return {
      title: "Teste",
      count: 0,
    }
  },
  methods: {

  },
  components: {
    LocalComponent
  }
}
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
</style>
