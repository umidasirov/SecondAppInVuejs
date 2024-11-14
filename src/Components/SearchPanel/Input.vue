<script>
  export default {
    data(){
      return{
        searchSystem:''
      }
    },
    props:{
      img:{
        type:String,
        required:true
      }
    }
  }
</script>

<template>
<input type="text" placeholder="Kinolarni qidirish" class="form-control" v-model="searchSystem"/>
</template>

<style scoped>
input{
  padding: 20px 20px;
}
</style>