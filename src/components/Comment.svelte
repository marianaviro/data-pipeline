<script>
    export let step;
    export let line;
    console.log("Hola")
</script>

{#if Object.keys(step).length != 0}
    <p>{step['#']}</p>
{/if}
<style>
    p {
        opacity: 0.3;
        font-size: 1em;
        font-style: italic;
    }
    .line-number {
        margin-right: 0.5em;
    }
</style>