
<template>
  <header>
    <h1>Navbar</h1>
    <router-link to="/">Home </router-link>
    <router-link to="/about"> About </router-link>
  </header>
</template>

<script>
export default {};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-evenly;
  border: 2px solid black;
  align-items: center;
}
</style>