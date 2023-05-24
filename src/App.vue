<script>
export default {
  data() {
    return {
      products: [],
      productInfo: {},
    };
  },
  methods: {
    addProduct() {
      this.products.push(this.productInfo);
      this.productInfo = {};
    },
    deleteProduct(index) {
      this.products.pop(index + 1);
    },
  },
};
</script>

<template>
  <div style="display: flex; flex-direction: column; gap: 2rem">
    <div style="font-size: x-large">Products</div>
    <div v-for="(product, index) in products" :key="product">
      <div style="background-color: antiquewhite">{{ product.name }}</div>
      <div style="background-color: antiquewhite">
        {{ product.description }}
      </div>
      <div style="background-color: antiquewhite">{{ product.price }}</div>
      <button style="background: red" @click="deleteProduct(index)">
        remove a product
      </button>
    </div>

    {{ JSON.stringify(productInfo) }}
    <input v-model="productInfo.name" type="text" />
    <input v-model="productInfo.description" type="text" />
    <input v-model="productInfo.price" type="text" />

    <button style="background: greenyellow" @click="addProduct">
      add a product
    </button>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
