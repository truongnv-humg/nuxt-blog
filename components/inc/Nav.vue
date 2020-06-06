<template>
  <div class="w-100 bg-dark">
    <div class="container">
      <nav class="navbar navbar-light bg-light w-100 bg-dark b-navbar">
        <nuxt-link :to="{name:'index'}" class="navbar-brand text-white">Blog</nuxt-link>
        <form class="form-inline position-relative">
          <input class="form-control" type="search" placeholder="Search" aria-label="Search">
          <button class="btn btn-light position-absolute b-btn-search" type="submit"><i class="fas fa-search"></i></button>
        </form>
      </nav>
    </div>
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped lang="scss">
  .b-navbar {
    .b-btn-search {
      right: 0;
      top: 0;
      background: unset;
      border: 0;
      box-shadow: unset;
      &:active {
        background: unset;
        border: 0;
        box-shadow: unset;
      }
      &:hover {
        background: unset;
        border: 0;
      }
      &:focus {
        background: unset;
        border: 0;
        box-shadow: unset;
      }
    }
  }
</style>
