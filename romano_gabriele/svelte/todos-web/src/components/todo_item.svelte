<script>
    import Cell from "./cell.svelte";
    import Icon from "./icon.svelte";
    import Priority from "./priority.svelte";

    export let todo;

    const toggle_status = () => {
        todo.done = !todo.done;
    }
</script>

<Cell>
    {todo.id}
</Cell>
<Cell>
    {#if todo.done == false}
        <Icon name="circle" handler={toggle_status}></Icon>
    {:else}
        <Icon name="task_alt" handler={toggle_status}></Icon>
    {/if}
</Cell>
<Cell>
    {todo.task}
</Cell>
<Cell>
    <Priority></Priority>
</Cell>
<Cell>
    <Icon name="delete_forever"></Icon>
</Cell>