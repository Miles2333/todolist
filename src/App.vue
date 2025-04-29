<template>

  <div id="app">

    <h1> 根组件 </h1>
    <!--把下面的数据传到todolist的组件里面-->
    <todoList :todoList="todoList"></todoList>



  </div>


</template>





<script>

// 导入组件
import todoList from './components/todoList.vue';



export default{
  name: 'App',


  //传入相关数据
  data() {
    return {
      todoList: [
        {id:1, task:'吃饭', isCompleted:true},
        {id:2, task:'睡觉', isCompleted:false},
        {id:3, task:'打豆豆', isCompleted:false},

      ],

    };
  },

  components: {
    todoList
  }

}


</script>




<style>


</style>