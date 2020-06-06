<template>
  <div class="container mt-5">
    <Header></Header>
    <ContentPost class="mt-4"></ContentPost>
  </div>
</template>

<script>
  import Header from '../../components/post/Header';
  import ContentPost from '../../components/post/Content';
  export default {
    components: {
      Header, ContentPost
    }
  }
</script>
