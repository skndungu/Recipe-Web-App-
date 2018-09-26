<template>
  <section class="single-recipe">
      <h1>{{ recipe.title}}</h1>
      <div>
          <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
      </div>
        <p>{{ recipe.descriptionText }}</p>
  </section>
</template>


<script>
export default {
        asyncData (context) {
        return new Promise ((resolve, reject) => {
            setTimeout (() => {
                resolve({
                    recipe: [
                        {
                            id: "1",
                            title: 'Delicious Pizza',
                            previewText: "Awesome",
                            descriptionText: "This is really a delicious meal",
                            thumbnail: "https://upload.wikimedia.org/wikipedia/commons/6/64/Foods_%28cropped%29.jpg"

                        },
                        {
                            id: "2",
                            title: 'Common Food',
                            previewText: "Very tasty",
                            descriptionText: "This is really a delicious meal",
                            thumbnail: "https://2vf8ai39couv1r0o03981owr-wpengine.netdna-ssl.com/wp-content/uploads/2017/10/our-food.jpg"

                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500)
        })
    }
}
</script>

<style scoped>
 .single-recipe {
     display: flex;
     flex-flow: column;
     justify-content: center;
     align-items: center;
     text-align: center;
     padding: 30px;
 }

 .recipe-image {
     width: 100%;
 }
</style>
