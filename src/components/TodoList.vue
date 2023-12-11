<template>
   <div class="container">
    <div class="col-12">
        <p>For add new todo write and press enter</p>
    </div>

    <div class="row">
          <NewTodo @on-addtodo="addTodo($event)"/>
    </div>
    <div class="row">
        <div class="col-12 col-lg-6">
           <ul class="list-group">
            <Todo v-for="(item,index) in todos"
             :key="index"
             :todoString="item.todoString"
             :completed="item.completed"
             @on-delete="deleteTodo(item)"
             @on-toggle="ToggleTodo(item)"
             @on-edit="editTodo(item,$event)"
             />
           </ul>
        </div>
    </div>
   </div>
</template>
<script>
import Todo from './Todo.vue';
import NewTodo from './NewTodo.vue';

export default{
    components:{
               Todo,
               NewTodo
},

    data(){
        return{
            todos:[
                {todoString:"Make anugular course",completed:"true"},
                {todoString:"Make food course",completed:"false"},
                {todoString:"Make driving course",completed:"false"},
                {todoString:"Make php course",completed:"true"},
            ]
        }
    },
    methods:{

        addTodo(newTodo){
          this.todos.push({
            todoString:newTodo,
            completed:false,
          });
        },

        ToggleTodo(todo){
            todo.completed = !todo.completed;
        },
        editTodo(todo, newTodoString){
            todo.todoString = newTodoString;
        },
        deleteTodo(deleteTodo){
            this.todos = this.todos.filter(todo => todo !== deleteTodo)
        },

    }

}
</script>

<style>

</style>