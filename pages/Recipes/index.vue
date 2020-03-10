<template>
  <!-- The template will only be rendered when the fetch is done -->
  <section class="recipes">
  <Recipe v-for="recipe in recipes"
  :key="recipe.id"
  :thumbnail="recipe.thumbnail"
  :title="recipe.title"
  :id="recipe.id"
  :previewText="recipe.previewText" />
</section>
</template>

<script>
import Recipe from '@/components/recipe'

export default {
  components: {Recipe},
  asyncData() {
    // specical method, executed on the server, fetch to the server then return to the client
    // return axios.get(), this return item is also a promise
    // promise takes a function
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id:"1",
              title: "Delicious Pizza",
              previewText: "Awesome Pizza!",
              thumbnail: "https://www.blazepizza.com/assets/images/BYO_Large_1684x1114.jpg"
            },
            {
              id:"2",
              title: "Salad",
              previewText: "Awesome Salad!",
              thumbnail: "https://www.cookingclassy.com/wp-content/uploads/2019/11/best-salad-7.jpg"
            }
          ]
        }, 1500)
      })
    })
  },
  head () {
    return {
      title: 'recipes',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'recipes', name: 'recipes', content: 'recipes description' }
      ]
    }
  }
}

</script>

<style lang="scss" scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}


</style>
