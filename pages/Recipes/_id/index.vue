<template>
  <section class="single-recipe">
    <h1>{{recipe.title}}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{recipe.description}}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    // specical method, executed on the server, fetch to the server then return to the client
    // return axios.get(), this return item is also a promise
    // promise takes a function
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id:"1",
              title: "Delicious Pizza",
              previewText: "Awesome Pizza!",
              descriptionText: "this is description for pizza",
              thumbnail: "https://www.blazepizza.com/assets/images/BYO_Large_1684x1114.jpg"
            },
            {
              id:"2",
              title: "Salad",
              previewText: "Awesome Salad!",
              thumbnail: "https://www.cookingclassy.com/wp-content/uploads/2019/11/best-salad-7.jpg"
            }
          ].find(el => el.id === context.params.id)
        })
      },1500)
    })
  }
}
</script>

<style lang="scss" scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}

.recipt-img {
  width: 100%;
}
</style>
