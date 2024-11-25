<svelte:head>
    <link href="https://fonts.googleapis.com/icon?family=Material+Symbols+Outlined"
      rel="stylesheet">
</svelte:head>

<script>
    export let name;
</script>

<span class="material-symbols-outlined icon">
    {name}
</span>

<style>
    div {
        border: 2px solid green;
        width: 64px;
        height: 64px;
        margin: 5px;
    }

    .icon {
        font-size: 32px;
    }

    .icon:hover {
        cursor: pointer;
    }

    .material-symbols-outlined {
        font-variation-settings:
        'FILL' 0,
        'wght' 400,
        'GRAD' 0,
        'opsz' 24
    }
</style>