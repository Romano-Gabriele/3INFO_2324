<svelte:head>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@48,400,0,0">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bungee+Spice&display=swap">
</svelte:head>

<script>
    import { createEventDispatcher } from "svelte";

    const despatch = createEventDispatcher();
    export let counter = 0;

    function counter_incr() {
        counter += 2;
    }

    function counter_decr() {
        counter -= 3;
    }

    function emit_event() {
        despatch("doublecontatore", {
            valore: counter
        })
    }
</script>

<div class="container">
    <div class="pulsante">
        <button on:click={counter_decr}>
            <span class="material-symbols-outlined icon">remove</span>
        </button>
    </div>
    <div class="number">
        {counter}
    </div>
    <div class="pulsante">
        <!-- <button on:click={() => counter++}>Premi Qui</button> -->
        <button on:click={counter_incr}>
            <span class="material-symbols-outlined icon">add</span>
        </button>
    </div>
</div>

<style>
    .container {
        border: 4px solid #D43C2F;
        display: flex;
        justify-content: space-between;
        border-radius: 30px;
        width: 300px;
        padding: 10px;
    }

    .pulsante {
        display: flex;
        align-items: center;
    }

    button {
        border: none;
        background: none;
    }
    
    .material-symbols-outlined {
        font-family: 'Material Symbols Outlined';
        font-weight: normal;
        font-style: normal;
        font-size: 24px;
        line-height: 1;
        letter-spacing: normal;
        text-transform: none;
        display: inline-block;
        white-space: nowrap;
        word-wrap: normal;
        direction: ltr;
        -moz-font-feature-settings: 'liga';
        -moz-osx-font-smoothing: grayscale;
    }

    .icon {
        font-size: 2.5rem;
        color: #F09C00;
        font-weight: bolder;
    }

    .icon:hover {
        color: #D43C2F;
        cursor: pointer;
    }

    .icon:active {
        text-shadow: 1px 1px 10px #D43C2F;
    }

    .number {
        font-size: 4rem;
        font-family: "Bungee Spice", cursive;
    }
</style>