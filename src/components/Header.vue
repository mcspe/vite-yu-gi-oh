<script>
export default {
  name: "Header",
  props:{
    titolo: String
  }
}
</script>

<template>
  <header class="m-3 d-flex align-items-center">
    <img src="/logo-yugioh.jpg" alt="Logo YuGiOh" class="object-fit-cover h-50">
    <h1>{{ titolo }}</h1>
  </header>
</template>

<style lang="scss" scoped>
  header{
    height: 5rem;

    h1{
      font-weight: bold;
    }
  }
</style>