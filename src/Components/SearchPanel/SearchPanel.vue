<script>
import Input from "@/Components/SearchPanel/Input.vue";
import Filter from "@/Components/SearchPanel/Filter.vue";
export  default {
  components:{
    Input,
    Filter
  },
  data(){
    return{
    }
  },
  props:{
    updateTermHandler:{
      type:Function,
      required:true
    },
    updateFilterHandler:{
      type:Function,
      required:true
    }
  }
}
</script>

<template>
  <div class="search-panel input">
    <Input img="img" :term="term" :updateTermHandler="updateTermHandler"/>
    <Filter :updateFilterHandler="updateFilterHandler"/>
  </div>
</template>

<style scoped>
.search-panel{
  margin: 0 auto;
  margin-top: 50px;
  width: 100vh;
  box-shadow: 1px 1px 30px rgba(0, 0, 0, 0.15);
  padding: 20px 20px 20px 20px;
}
</style>