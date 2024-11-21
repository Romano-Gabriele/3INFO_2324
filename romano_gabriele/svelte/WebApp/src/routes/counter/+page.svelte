<script>
    import { bind } from "svelte/internal";
import Counter from "../../lib/components/counter.svelte";
    import DoubleCounter from "../../lib/components/double_counter.svelte";
    let contatore = 0;
    let doubleContatore = 0;
</script>

<h1>Pagina Counter!!!</h1>

<h2>Il valore del contatore vale: {contatore}</h2>

<Counter bind:counter={contatore}></Counter>

<h2>Il valore del contatore double vale: {doubleContatore}</h2>

<DoubleCounter bind:counter={doubleContatore}></DoubleCounter>