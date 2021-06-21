<template>
  <todoheader />
  <todoinput />
  <todolist />
  <todofooter />
</template>

<script>
import todoheader from './components/todoheader.vue'
import todoinput from './components/todoinput.vue'
import todolist from './components/todolist.vue'
import todofooter from './components/todofooter.vue'

export default {
  name:'App',
  components:{
    todoheader,
    todoinput,
    todolist,
    todofooter,

  }
}
</script>

<style>
/* gogle fonst로 폰트 변형하는법 */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');
body{font-family: 'Roboto', sans-serif;background: #f6f6f8; text-align:center;}
*{margin: 0;padding: 0;box-sizing: border-box;}
li{list-style: none;}
a:link,a:visited{color:#333;text-decoration:none;}
.clearfix::after{display: block;content:"";clear:both;}

#app{padding: 0 20px;}
input{border-style: groove;width:70%;}
button{border-style:groove;}
.shadow{box-shadow: 5px 10px 10px rgba(0,0,0,0.03);}
</style>