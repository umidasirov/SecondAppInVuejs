<script>
export default {
  data() {
    return {
      selected: 'a' // Будем использовать одно состояние для хранения выбранной кнопки
    }
  },
  props:{
    Films:{
      type:Array,
      required:true
    }
  },
  methods: {
    selectButton(button) {
      this.selected = button;
    },

  }
}
</script>

<template>
  <div class="btn-group">
    <button
        :class="['btn', selected === 'a' ? 'btn-dark' : 'btn-outline-dark']"
        @click="selectButton('a')"
    >
      barcha kinolar
    </button>
    <button
        :class="['btn', selected === 'b' ? 'btn-dark' : 'btn-outline-dark']"
        @click="selectButton('b')"
    >
      mashxur kinolar
    </button>
    <button
        :class="['btn', selected === 'c' ? 'btn-dark' : 'btn-outline-dark']"
        @click="selectButton('c')"
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
