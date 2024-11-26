<script>
    import Cell from "./cell.svelte";
    import Icon from "./icon.svelte";
    import Priority from "./priority.svelte";

    export let todo;
</script>

<Cell>
    {todo.id}
</Cell>
<Cell>
    {#if todo.done == false}
        <Icon name="circle"></Icon>
    {:else}
        <Icon name="task_alt"></Icon>
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