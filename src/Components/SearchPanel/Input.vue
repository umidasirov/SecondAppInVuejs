<script>
  export default {
    data(){
      return{
        searchSystem:this.term,
        term:''
      }
    },
    props:{
      img:{
        type:String,
        required:true
      },
      updateTermHandler:{
      type:Function,
      required:true
    }
    },
    methods:{
    changeHandler(e){
      this.term = e.target.value
      this.updateTermHandler(this.term)
    }
  }
  }
</script>

<template>
<input type="text" placeholder="Kinolarni qidirish" class="form-control" @input="changeHandler" :value="term"/>
</template>

<style scoped>
input{
  padding: 20px 20px;
}
</style>