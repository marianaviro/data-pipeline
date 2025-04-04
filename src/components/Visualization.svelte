<script>
    export let step;
    export let line;
</script>

{#if Object.keys(step).length != 0}
    <p><span class="line-number">{line}</span>{JSON.stringify(step)}</p>
{/if}

<style>
    p {
        color: #7570b3;
    }
    .line-number {
        margin-right: 0.5em;
    }
</style>