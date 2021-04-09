<template>
  <div>
    <ul v-for="(product,index) in products" v-bind:key="product.name">
      <Item 
        v-bind:item="product.name"
        v-bind:quantity="product.products.length"
        v-bind:label="maxMin(index)"
        v-bind:name="maxminName(product, index)"
        v-bind:price="maxminPrice(product, index)"
      />
    </ul>
  </div> 
</template>

<script>
import {data} from '../data/data'
import Item from './Item'
export default {
  data() {
    return {
      products: data.products,
      isBlue: false
  }},
  name: 'product-list',
  components: {
    Item
  },
  methods: {
    maxminPrice(product, index) {
      const item = product.products.map(e=>e.price)
      return index%2==0?Math.max(...item):Math.min(...item)
    },
    maxminName(product, index) {
      const prices = product.products.map(e=>e.price)
      const max = Math.max(...prices)
      const min = Math.min(...prices)
      const maxName = product.products.find(item => item.price==max).name
      const minName = product.products.find(item => item.price==min).name
      return index%2==0?maxName:minName
    },
    maxMin(index) {
      return index%2==0?'mayor':'menor'
    },
    changeBlue() {
      this.isBlue=!this.isBlue
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: flex;
  margin: 0 10px;
}
</style>
