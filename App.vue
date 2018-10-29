<template>
	<div id="app">
    Handler:
    <select v-model="handlerId">
      <option value="1">1</option>
      <option value="2">2</option>
    </select><br><br>
    <button @click="clickHandler">clik me!</button>
	</div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      handlerId: '1',
      clickHandler: this.handler1
    }
  },
  methods: {
    handler1() {
      console.log('handler 1');
    },
    handler2() {
      console.log('handler 2');
    }
  },
  watch: {
    handlerId(value) {
      this.clickHandler = this[`handler${value}`];
    }
  }
};
</script>

<style>
body,
input {
  font-family: "Exo 2", sans-serif;
  font-size: 16px;
}
</style>
