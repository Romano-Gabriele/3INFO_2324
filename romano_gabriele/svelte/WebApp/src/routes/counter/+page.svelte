<script>
    import { bind } from "svelte/internal";
import Counter from "../../lib/components/counter.svelte";
    import DoubleCounter from "../../lib/components/double_counter.svelte";
    let contatore = 0;
    let doubleContatore = 0;
    let numeri = [1, 7, 2, 6, 9, 10]
    let sottolineato = true;
    let doppio;

    $: {
        doppio = contatore * 2;
        sottolineato = !(contatore % 2);
    }

    function gestisci_evento(evento) {
        alert(`${evento.detail.tipo} -- ${evento.detail.valore}`);
    }
</script>

<h1>Pagina Counter!!!</h1>

<!-- {#if contatore < 5}
    <h2 class="rosso">Il valore del contatore vale: {contatore}</h2>
{:else}
    <h2 class="verde">Il valore del contatore vale: {contatore}</h2>
{/if} -->

<!-- <h2 class={contatore < 5 ? "rosso" : "verde"}>Il valore del contatore vale: {contatore}</h2> -->

<!-- <h2 class:rosso={contatore < 5}>Il valore del contatore vale: {contatore}</h2> -->

<h2 class:sottolineato>Il valore del contatore vale: {contatore}</h2>

<h2>Il suo doppio vale {doppio}</h2>

<Counter bind:counter={contatore} on:contatore={gestisci_evento}></Counter>

<h2>Il valore del contatore double vale: {doubleContatore}</h2>

<DoubleCounter bind:counter={doubleContatore}></DoubleCounter>

<ul>
    {#each numeri as numero, indice}
        <li>numeri[{indice}]:{numero}</li>
    {/each}
</ul>

<style>
    .rosso {
        color: red;
    }

    .verde {
        color: green;
    }

    .sottolineato {
        text-decoration: underline;
    }
</style>