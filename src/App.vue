<script>
import AppInfo from "@/Components/AppInfo.vue";
import SearchPanel from "@/Components/SearchPanel/SearchPanel.vue";
import MovieList from "@/Components/MovieList/MovieList.vue";
import AddForm from "@/Components/MovieAddForm/AddForm.vue";
export default {
  components:{
    AddForm,
    MovieList,
    AppInfo,
    SearchPanel
  },
  data(){
    return{
      Films:[{name:"interstellar",views:123,year:2000,favourite:true},{name:"Empire of Osman",views:423,year:1999,favourite:true},{name:"moon",views:923,year:2013,favourite:false}]
    }
  },
  methods:{
  }
}
</script>

<template>
  <AppInfo />
  <SearchPanel  :Films="Films"/>
  <MovieList :Films="Films"/>
  <AddForm :Films="Films"/>
</template>

<style scoped>

</style>
