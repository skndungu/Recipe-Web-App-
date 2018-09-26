<template>
    <section class="recipes">
        <Recipe
        v-for="recipe in recipes"
        :key="recipe.id"
        :thumbnail="recipe.thumbnail"
        :title="recipe.title"
        :id="recipe.id"
        :previewText="recipe.previewText"
         />
    </section>
</template>

<script>
import Recipe from '@/components/Recipe';
export default {
    components: {
        Recipe
    },
    asyncData () {
        return new Promise ((resolve, reject) => {
            setTimeout (() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: 'Delicious Pizza',
                            previewText: "Awesome",
                            thumbnail: "https://upload.wikimedia.org/wikipedia/commons/6/64/Foods_%28cropped%29.jpg"

                        },
                        {
                            id: "2",
                            title: 'Common Food',
                            previewText: "Very tasty",
                            thumbnail: "https://2vf8ai39couv1r0o03981owr-wpengine.netdna-ssl.com/wp-content/uploads/2017/10/our-food.jpg"

                        }
                    ]
                })
            }, 1500)
        })
    }
}
</script>


<style scoped>
.recipes{
 display: flex;
 flex-flow: row wrap;
 justify-content: center;
 align-items: center;
}

</style>
