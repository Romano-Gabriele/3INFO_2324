<script>
    import { bind } from "svelte/internal";

    let nome, cognome, eta, residenza;
    let confermato = false;
</script>

<h1>Input Page</h1>

Nome <input bind:value={nome}>
Cognome <input bind:value={cognome}>
Età <input bind:value={eta}>
Residenza <input bind:value={residenza}>

<br><br>

Confermato <input type="checkbox" bind:checked={confermato}>

<p>
    Io sono {nome} {cognome} ed ho {eta} anni e abito a {residenza}
</p>

<button disabled={!confermato}>Invia</button>