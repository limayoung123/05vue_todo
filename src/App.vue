<template>
  <todoheader />
  <todoinput @addTodo="addTodo"/>
  <!-- 함수넣기 ="명작"
  input에서 값을 받았음 -->
  <todolist :todoItems="todoItems" @removeTodo="removeTodo"/>
  <!-- 값을 받아오고 함수로 실행시켜줘야함 -->
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

  },
  data(){
      return{
        todoItems:[]
      }
    },
    created(){
      // this.todoItems.push('안녕하세요!');
      // this.todoItems.push('반값습니다!');
      // todoItems에 push로 데이터값을 가져온것
      for(let i =0;i<localStorage.length;i++){
        if(localStorage.key(i) !== 'loglevel:webpack-dev-server'){ 
        this.todoItems.push(localStorage.key(i));
        }
      }
    },
    methods:{
      addTodo(todoItem){
        localStorage.setItem(todoItem,todoItem)
        // (value값을 인자값(명작)으로 사용해야함)
        this.todoItems.push(todoItem)
        // todoItems:[]값에 나오는것 입력하면 바로나오는것

      },
      removeTodo(todoItem,index){
        localStorage.removeItem(todoItem)
        this.todoItems.splice(index,1)
        // 배열을 삭제할때 splice(index,1는 1개를 지울때)
      }
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