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
      Films:[{name:"interstellar",views:123,year:2000,favourite:true,id:1},{name:"Empire of Osman",views:423,year:1999,favourite:true,id:2},{name:"moon",views:923,year:2013,favourite:false,id:3}],
      term:'',
      filter:''
    }
  },
  methods:{
    onChangeHandler(arr,term){
      if (term.lenght == 0) {
        return arr
      }
      if (typeof term !== "string") {
      return arr;
      }
      return arr.filter(c=>c.name.toLowerCase().indexOf(term) > -1)
    },
    updateTermHandler(term){
      this.term = term
      console.log("hello");
      
    },
    onFilterhandler(arr,filter){
      switch (filter) {
        case "popular":
          return arr.filter(c=>c.favourite)
          break;
        case "mostViewers":
          return arr.filter(c=>c.views>500)
          break;
        default:
          return arr
      }
    },
    updateFilterHandler(filter){
      this.filter = filter
    }
  }
}
</script>

<template>
  <AppInfo :AllFilms="Films.length" :FavoureiteFilm="Films.filter(x=>x.favourite).length"/>
  <SearchPanel :updateTermHandler="updateTermHandler" :updateFilterHandler="updateFilterHandler"/>
  <MovieList :Films="onFilterhandler(onChangeHandler(Films,term),filter)"/>
  <AddForm :Films="Films"/>
</template>

<style scoped>

</style>
