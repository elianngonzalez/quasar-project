<template>
  <q-page>
    <div class="center-items">
        <div v-for="category in categories" :key="category.idCategory">
          <img v-bind:src="category.strCategoryThumb" width="150" >
          <p class="Card">{{category.strCategory}}</p>
        </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import axios from 'axios';

export default defineComponent({
  name: "IndexMeals",
  data(){
    return {
      categories:[]
    }
  },
  mounted() {
    axios.get('https://themealdb.com/api/json/v1/1/categories.php')
      .then((res) => {
        console.log(res.data.categories)
        //idCategory - strCategory - strCategoryDescription - strCategoryThumb
        this.categories = res.data.categories
      })
      .catch((err) => {
        console.log(err)
      })
  },
})
</script>

<style scoped>
.center-items{
  display: grid;
  gap:20px;
  grid-template-columns: repeat(auto-fit , 230px) ;
  padding: 10px;
  justify-content: center;
  text-align:center;
}

</style>
