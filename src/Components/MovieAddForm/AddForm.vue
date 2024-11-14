<script>
import {filename} from "pathe/utils";

export default {
  data(){
    return{
      filmName:"",
      viewNum:''
    }},
props:{
  Films:{
    type:Array,
    required:true
  },
},
  methods:{
    addDatas(){
        this.Films.push({name:this.filmName,views:this.viewNum,year:2000,favourite:false})
        this.filmName = ""
        this.viewNum = ''

    }
  }
}
</script>

<template>
  <div class="input-group">
    <input type="text" class="form-control" placeholder="Kino nomi" v-model="filmName">
    <input type="number" class="form-control" placeholder="necha marotaba ko'rilgan?" v-model="viewNum">
    <button class="btn btn-outline-success" v-if="viewNum=='' && filmName==''">malumot kiriting</button>
    <button class="btn btn-outline-success" @click="addDatas()" v-else>qoshish</button>
  </div>
</template>

<style scoped>
div{
  margin: 0 auto;
  margin-top: 50px;
  width: 100vh;
  box-shadow: 1px 1px 30px rgba(0, 0, 0, 0.15);
  padding: 30px 30px 30px 30px;
}
</style>