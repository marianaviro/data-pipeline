<script>
    import Variable from "../components/Variable.svelte"
    export let step;
    console.log(step)
</script>
{#if Object.keys(step).length != 0}
    <div class="line">
        <p class="content">{step.step}</p>
        <Variable type={"File"} content={step.filename} />
    </div>
{/if}
<style>
    .line {
        margin: 15px 0;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: start;
        align-items: end;
        background-color: #F2F2F2;
        border-radius: 5px;
    }
    p {
        margin-top: 15px;
    }

    .content {
        margin-top: 5px;
        padding: 0.6em 0.8em 0.5em 0.8em;
    }
</style>