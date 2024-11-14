
<template>
  <div class="list-item">
    <MovieListItem :List="Films"/>
    <span v-if="Films.length == 0">Film qo'shing</span>
  </div>
</template>



<script>
import MovieListItem from "@/Components/MovieList/MovieListItem.vue";
export default {
  props:{
    Films:{
      type:Array,
      required:true
    }
  },
components:{
  MovieListItem
}
}
</script>



<style scoped>
.list-item{
  margin: 0 auto;
  margin-top: 50px;
  width: 100vh;
  box-shadow: 1px 1px 30px rgba(0, 0, 0, 0.15);
  padding: 30px 30px 40px 30px;
}
</style>
