<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" placeholder="글자를 입력하세요" 
        v-on:keyup.enter="addTodo">
        <!-- keyup은 enter눌렀을때 -->
        <button class="addContainer" v-on:click="addTodo">
            <!-- 버튼을 눌렀을때 local에 push해서 하기 -->
            <!-- fontawesome사용 -->
            <i class="addBtn fas fa-plus"></i>
        </button>
    </div>
 
</template>

<script>
export default {
    name:'input',
    data(){
        return{
            newTodoItem:'',
            
        }
    },
    methods:{
        addTodo(){
            console.log(this.newTodoItem);
            // data값에 변수를 넣었을때 그 값을 갖고오기위해서 this값을 넣어서 newTotoItem
            // 값을 갖고오는것
            let value = this.newTodoItem;
            localStorage.setItem(value,value);
            // this.$emit('addTodo',value);
            // $emit('',전송되는값)
            this.clearInput();
        },
        clearInput(){
            this.newTodoItem = '';
        }
    }
}
</script>


<style scoped>
    input:focus{outline:none;}
    /* 클릭시 반짝 거리는 외곽선 없어지는것 */
    .inputBox{background: #fff; line-height:50px; height:50px;
    border-radius: 5px; margin-bottom:10px;}
    .inputBox input{border-style: none; font-size:1rem;}

    .addContainer{float:right;border-style: none;
    background: linear-gradient(to right, #6478FB, #8763FB);
    display:inline-block; width:3rem; height: 50px;border-radius: 0 5px 5px 0;}
    .addBtn{color:#fff;}
</style>