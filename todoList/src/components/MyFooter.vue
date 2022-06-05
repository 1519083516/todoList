<template>
  <div class="todo-footer" v-show="total">
      <label>
          <!-- <input type="checkbox" :checked="isAll" @change="checkAll"> -->
          <input type="checkbox" v-model="isAll">
      </label>
      <span>
          <span>已完成{{doneTotal}}</span> / 全部{{total}}
      </span>
      <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>

<script>
export default {
    name:'MyFooter',
    props:['todos'],
    computed:{
        total(){
            return this.todos.length;
        },
        // doneTotal(){
        //     let count = 0;
        //     this.todos.forEach(todo => {
        //         if(todo.done) count++;
        //     });
        //     return i;
        // }
        doneTotal(){
            // 数组有几个元素，函数则调用几次,0为统计初始值,pre是(第一次为统计初始值)上一次函数返回值，current是数组现在对象
           return this.todos.reduce((pre,current)=> pre + (current.done?1:0),0);  
        },
        isAll:{
            get(){
                return this.doneTotal === this.total && this.total>0;
            },
            set(checked){
                this.$emit('checkAllTodo', checked);
            }
        }
    },
    methods:{
    //     checkAll(e){
    //         this.checkAllTodo(e.target.checked);
    //     }
        clearAll(){
            this.$emit('clearAllDone');
        }
    }
}
</script>

<style scoped>
/* footer */
.todo-footer {
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
    margin-top: 5px;
}

.todo-footer label {
    display: inline-block;
    margin-right: 20px;
    cursor: pointer;
}

.todo-footer label input{
    position: relative;
    top: -1px;
    vertical-align: middle;
    margin-right: 5px;
}

.todo-footer button{
    float: right;
    margin-top: 5px;
}
</style>