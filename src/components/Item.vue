<template>
  <div class="container">
        <li class="item" v-bind:class="{blue: isBlue}" @click="changeBlue(index)">
          <b>{{item}}</b>: tiene {{quantity}} productos - su <b>{{label}}</b> producto es <b>{{name}}</b> - con precio <b>{{price}}$</b>
        </li>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isBlue: false
  }},
  name: 'item',
  props: {
    item: String,
    quantity: Number,
    label: String,
    name: String,
    price: Number,
  },
  methods: {
    changeBlue() {
      this.isBlue=!this.isBlue
    }
  }
}
</script>

<style scoped>
.container {
  margin: auto;
}
.item {
  cursor: pointer;
  user-select: none;
}
.blue {
  color: blue;
}
</style>
