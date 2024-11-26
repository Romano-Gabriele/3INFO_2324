<script>
    import Icon from "./icon.svelte";
    import TodoItem from "./todo_item.svelte";

    let todos = []; //ToDoList
    let last_id = 0;

    const create_todo = async () => {
        let todo = { //ToDo Item
            id: ++last_id,
            task: '',
            done: false,
            priority: 3
        };
        console.log("CREATE", todo);
        //aggiorno la todo list
        todos = [...todos, todo];
    }
</script>

<h1>ToDos</h1>
<div class="todo-list">
    <div class="header"><Icon name="tag"></Icon></div>
    <div class="header"><Icon name="task_alt"></Icon></div>
    <div class="header"><Icon name="list"></Icon></div>
    <div class="header"><Icon name="schedule"></Icon></div>
    <div class="header"><Icon name="add_box" handler={create_todo}></Icon></div>

    <!-- ToDo Items -->
     {#each todos as todo}
        <TodoItem todo={todo}></TodoItem>
     {/each}
</div>

<style>
    .todo-list {
        border: 3px solid blue;
        width: 95%;
        height: 80%;
        margin: auto;
        display: grid;
        grid-template-columns: 0.75fr 0.75fr 2fr 1.5fr 0.75fr;
    }
</style>