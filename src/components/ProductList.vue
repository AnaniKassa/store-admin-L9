<template>
  <div class="action-button">
    <router-link to="/product/add">
      <button class="add-prod-btn">Add Product</button>
    </router-link>
  </div>
  <div class="product-list">
    <table>
      <thead>
        <tr>
          <th>Product ID</th>
          <th>Product Name</th>
          <th>Product Description</th>
          <th>Price</th>
        </tr>
      </thead>
      <tr v-for="product in products" :key="product.productId">
        <td><router-link :to="`/product/${product.id}`">{{ product.id }}</router-link></td>
        <td>{{ product.name }}</td>
        <td>{{ product.description }}</td>
        <td>{{ product.price }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'ProductList',
    props: ['products'],
    mounted() {
      this.$emit('getProducts')
    }
  }
</script>

<style scoped>
a {
  color: #0000FF;
  text-decoration: underline;
}

.product-list {
  text-align: left;
}

.add-prod-btn {
  background-color: #0046be;
  color: #fff;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  font-weight: bold;
  border-radius: 5px;
  display: flex;
  align-items: center;
  gap: 8px;
}

</style>