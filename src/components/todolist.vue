<template>
 <section>
   <ul>
     <li v-for="(items,i) in todoItems" :key="i">
       <i class="checkBtn fa fa-check"></i>{{todoItems[i]}}
       <span class="removeBtn" @click="removeTodo(todoItems[i],i)">
         <!-- 클릭시 인자값이 2개 넣은것
         removeTodo()안에 넣어주고
         App.vue값에 전송되게해줘야함 -->
         <i class="fa fa-trash"></i>
       </span>
     </li>
   </ul>
 </section>
</template>

<script>
export default {
    name:'todolist',
    props:['todoItems'],
    methods:{
      removeTodo(todoItem,index){
        this.$emit('removeTodo',todoItem,index)
      }
    }
    // data(){
    //   return{
    //     todoItems:[]
    //   }
    //  },
    //  created(){
    // //   // this.todoItems.push('안녕하세요!');
    // //   // this.todoItems.push('반값습니다!');
    // //   // todoItems에 push로 데이터값을 가져온것
    //    for(let i =0;i<localStorage.length;i++){
    //      if(localStorage.key(i) !== 'loglevel:webpack-dev-server'){ 
    //      this.todoItems.push(localStorage.key(i));
    //     }
    //    }
    //  }
}
</script>

<style>
ul{text-align:left}
li{display: flex; line-height: 50px;margin: 0.5rem 0;
padding: 0 1rem; background: #fff; border-radius: 5px;}
.checkBtn{line-height: 45px; color:#62acde; 
margin-right:5px;}
.removeBtn{margin-left: auto; color:#de4343}
</style>