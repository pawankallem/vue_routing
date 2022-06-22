
<template>
  <div>
    <h1>Home page</h1>
    <h1 v-show="isLoading">Loading . . . .</h1>
    <table v-show="!isLoading">
      <thead>
        <tr>
          <th>S.No</th>
          <th>Title</th>
          <th>Price</th>
          <th>Description</th>
          <th>Category</th>
          <th>Image</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(x, i) in apiData" v-bind:key="i">
          <td>{{ x.id }}</td>
          <td>{{ x.title }}</td>
          <td>{{ x.price }}</td>
          <td>{{ x.description }}</td>
          <td>{{ x.category }}</td>
          <td><img v-bind:src="x.image" alt="" /></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      apiData: [],
      isLoading: true,
    };
  },
  beforeMount() {
    axios
      .get("https://fakestoreapi.com/products")
      .then((res) => {
        this.apiData = res.data;
        this.isLoading = false;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style scoped>
table,
th,
td {
  border: 1px solid;
}
img {
  width: 50px;
}
</style>