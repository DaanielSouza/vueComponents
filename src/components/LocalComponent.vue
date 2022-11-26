<template>
  <h1>Local</h1>
  <h2>{{ title }}</h2>
  <slot name="header"></slot>
  <br>
  <!-- <button @click="$emit('addClick')">Add</button> -->
  <button @click="$emit('addClick', 1)">Add</button>
  <button @click="addTwo">Add2</button>
  <br>
  <slot name="content"></slot>
  <!-- <slot></slot> -->
</template>

<script>
export default {
  props: {
    title: String
  },
  methods: {
    addTwo: function () {
      this.$emit('addClick', 2);
    }
  }, computed: {
    computedTeste() {
      return "Teste";
    }
  }, beforeCreate() {
    console.log("beforeCreate", this.title);
  }, created() {
    console.log("created", this.title);
  }, beforeMount() {
    console.log("beforeMount", this.title);
  }, mounted() {
    console.log("mounted", this.title);
  }, beforeUpdate() {
    console.log("beforeUpdate", this.title);
  }, updated() {
    console.log("updated", this.title);
  }, beforeUnmount() {
    console.log("beforeUnmount", this.title);
  }, unmounted() {
    console.log("unmounted", this.title);
  }
}
</script>