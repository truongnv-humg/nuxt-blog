<template>
  <div>
    <h6 class="text-uppercase">{{ dateCreate }} - <span class="text-primary">{{ category }}</span></h6>
    <h1 class="font-weight-bold">{{ title }}</h1>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        dateCreate: '2020/06/05',
        category: 'React',
        title: 'Learn React Hooks by Building a Paint App'
      }
    },
  }
</script>
