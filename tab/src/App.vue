<template>
  <div id="main">
    <nav @click.prevent>
      <a v-for="item in items" @click="makeActive(item, $index)">{{item.name}}</a>
    </nav>
    <p>You chose <b>{{active}}</b></p>
  </div>
</template>

<script>
export default {
  name: 'main',
  data () {
    return {
      active:'HTML',
      items:[
        {name:'HTML', active:true},
        {name:'CSS', active:false},
        {name:'JavaScript', active:false},
        {name:'Vue.js', active:false}
      ]
    }
  },
  methods: {
    makeActive: function(item, index){
      this.active = item.name;
      for(var i=0; i<this.items.length;i++){
        this.items[i].active = false;
      }
      this.items[index].active = true;
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#main{
  width: 500px;
  margin: 0 auto;
  text-align: center;
}
nav{
  display:inline-block;
  margin:60px auto 45px;
  background-color:#f00;
  box-shadow:0 1px 1px #ccc;
  border-radius:2px;
}
nav a{
  display:inline-block;
  padding: 18px 30px;
  color:#fff !important;
  font-weight:bold;
  font-size:16px;
  text-decoration:none !important;
  line-height:1;
  background-color:transparent;
  -webkit-transition:background-color 0.25s;
  -moz-transition:background-color 0.25s;
  transition:background-color 0.25s;
  cursor:pointer;
}
b{
  display:inline-block;
  padding:5px 10px;
  background-color:#ff0;
  border-radius:2px;
  font-size:18px;
}

</style>
