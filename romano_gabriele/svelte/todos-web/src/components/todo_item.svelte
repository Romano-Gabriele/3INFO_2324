<script>
    import Cell from "./cell.svelte";
    import Icon from "./icon.svelte";
    import Priority from "./priority.svelte";
</script>

<Cell>
    id
</Cell>
<Cell>
    <Icon name="circle"></Icon>
</Cell>
<Cell>
    task
</Cell>
<Cell>
    <Priority></Priority>
</Cell>
<Cell>
    <Icon name="delete_forever"></Icon>
</Cell>