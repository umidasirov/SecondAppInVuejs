<script>
export default {
  props:{
    List:{
      type:Array,
      required:true
    }
  },
  data(){
    return{
    }
  },
  methods:{
    toggleFavourite(item) {
      item.favourite = !item.favourite;
    },
    deleteItem(index) {
      this.List.splice(index, 1);
    }
  }
}
</script>

<template>
  <li :class="['list-group-item', 'd-flex', 'justify-content-between', item.favourite ? 'like favourite' : '']" v-for="(item,index) in List">
  <span className="list-group-item-label">{{item.name}}</span>
  <input type="number" v-model="item.views" />
  <div className="d-flex justify-content-center aling-items-center">
    <button className="btn-cookie btn-sm" @click="toggleFavourite(item)">
      <i className="fas fa-cookie"></i>
    </button>
    <button className="btn-cookie btn-sm" @click="deleteItem(index)">
      <i className="fas fa-trash"></i>
    </button>
    <i className="fas fa-star"></i>
  </div>
  </li>
</template>

<style scoped>
.list-group-item{
  padding: 15px 20px;
  border-bottom: 1px solid #3d5a80;
}
.list-group-item:last-child{
}
.list-group-item span{
  text-transform: uppercase;
  line-height: 35px;
  font-size: 20px;
  cursor: pointer;
  width: 550px;
}
.list-group-item input{
  line-height: 35px;
  font-size: 20px;
  text-align: center;
  border: 0;
}
.list-group-item button{
  width: 35px;
  height: 35px;
  margin: 3px;
  font-size: 17px;
  border: none;
  cursor: pointer;
}
.list-group-item .btn-cookie{
  color: #e09f3e;
}
.list-group-item .btn-trash{
  color: #5e383b;
}
.list-group-item .fa-star{
  width: 35px;
  height: 35px;
  text-align: center;
  line-height: 35px;
  font-size: 16px;
  color: #ffd700;
  transition: 0.3s all;
  transform: translateX(30px);
  opacity: 0;
}
.list-group-item.like .fa-star{
  color: #ffd700;
  opacity: 1;
  transform: translateX(0px);
}
.list-group-item.favourite input,
.list-group-item.favourite{
  color: #e09f3e !important;
}
.list-group-item.favourite .fa-star{
  color: #ffd700;
}
.fa-trash{
  color: red;
}
</style>