<script>
export default {
  data(){
    return{
    allFilms:23,
      moreWatchedFilms:12
    }
  }
}
</script>

<template>
<div class="app-info">
  <h1>Barcha kinolar soni: {{allFilms}}</h1>
  <h2>ko'p ko'rilgan kinolar soni: {{moreWatchedFilms}}</h2>
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