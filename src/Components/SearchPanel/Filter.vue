<script>
export default {
  data() {
    return {
      filter:"",
      selected: 'a'
    }
  },
  props:{
    updateFilterHandler:{
      type:Function,
      required:true
    }
  },
  methods: {
    filterHandler(filter,button){
      this.selected = button;
      this.filter = filter
      this.updateFilterHandler(this.filter)
    },
  }
}
</script>

<template>
  <div class="btn-group">
    <button
        :class="['btn', selected === 'a' ? 'btn-dark' : 'btn-outline-dark']"
        @click="filterHandler('all','a')"

    >
      barcha kinolar
    </button>
    <button
        :class="['btn', selected === 'b' ? 'btn-dark' : 'btn-outline-dark']"
        @click="filterHandler('popular','b')"
    >
      mashxur kinolar
    </button>
    <button
        :class="['btn', selected === 'c' ? 'btn-dark' : 'btn-outline-dark']"
        @click='filterHandler("mostViewers","c")'
    >
      eng kop korilgan kinolar
    </button>
  </div>
</template>

<style scoped>
.btn-group {
  margin-top: 20px;
}
</style>
