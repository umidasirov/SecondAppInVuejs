<script>
export default {
  data(){
    return{
    allFilms:this.AllFilms,
    moreWatchedFilms:12
    }
  },
  props:{
    AllFilms:{
      type:Number,
      required:true
    },
    FavoureiteFilm:{
      type:Number,
      required:true
    }
  }
}
</script>

<template>
<div class="app-info">
  <h1>Barcha kinolar soni: {{AllFilms}}</h1>
  <h2>ko'p ko'rilgan kinolar soni: {{FavoureiteFilm}}</h2>
</div>
</template>

<style scoped>
.app-info{
  margin: 0 auto;
  margin-top: 50px;
  width: 100vh;
  box-shadow: 1px 1px 30px rgba(0, 0, 0, 0.15);
  padding: 30px 30px 30px 30px;
  h3{
    margin-top: 20px;
  }
}
</style>