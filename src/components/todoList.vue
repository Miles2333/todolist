<template>
    <ul class="list-group">

        <!-- 会让里面的东西自动左右分开排列，并且上下居中对齐。 
         1. list-group-item：此为 Bootstrap 框架里的类名，把元素样式设置成列表组里的一个项目。
         
         2. justify-content-between：该类作用于 Flexbox 容器，其功能是在主轴上均匀分布子元素，
         把第一个子元素放置在容器起始位置，最后一个子元素放在容器末尾位置，并且在它们之间留出相等的间距。
         
         3.   重要!!!   全部统一成 todoList ，视频里面的 todolist有误-->
        <li class="list-group-item d-flex justify-content-between align-items-center"
        
            v-for="item in todoList" 
            :key="item.id"
        
        >
        
        <!--复选框-->
        <div class="form-check">
            <input 
                class="form-check-input" 
                type="checkbox" 
                value="" 
                :id="item.id"
                />

            <label class="form-check-label" :for="item.id">
                <!--把Default checkbox 改成任务名-->
                {{ item.task }}  
            </label>
            </div>
        <span class="badge badge-primary badge-pill" v-if="item.isCompleted">已完成</span>
        <span class="badge badge-warning badge-pill"v-else>未完成</span>
        </li>

    </ul>
</template>



<script>

export default {
    name : "todoList",
    props: {
        todoList:{
            type: Array,
            required: true,
            default:[],
        },

    },
};


</script>


<!-- 调整列表的宽度和位置
 1.  margin: 0 auto 居中-->
<style scoped>
    .list-group{
        width: 500px;
        margin: 0 auto;
        
    }




</style>