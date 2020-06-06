<template>
  <div>
    <div class="d-flex justify-content-center">
      <div class="row b-list-news w-md-75">
        <div class="col-12">
          <nuxt-link :to="{name:'detail-slug', params: {slug: 'post-1'}}">
            <div class="row mb-4">
              <div class="col-12 col-md-4">
                <img src="https://www.freecodecamp.org/news/content/images/size/w1000/2020/06/hooks-logo.png" class="mr-3 b-thumb-news" alt="">
              </div>
              <div class="col-12 col-md-8">
                <h2 class="mt-0">{{ title }}</h2>
                Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
              </div>
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Learn React Hooks by Building a Paint App'
      }
    }
  }
</script>

<style scoped lang="scss">
  .b-list-news {
    .b-thumb-news {
      width: 100%;
    }
    a {
      color: unset;
      &:hover {
        text-decoration: none;
      }
    }
  }
</style>
