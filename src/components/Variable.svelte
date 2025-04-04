<script>
    export let id;
    export let type;
    export let content;
    let collapsed = $state(FALSE);
</script>

<div id={id} class="variable">
    <p class="type">{type}</p>
    <p class="content">{content}</p>
</div>
<style>

    .variable .type {
        text-transform: uppercase;
        font-size: 9.5px;
        margin-bottom: 1px;
    }

    .variable .content {
        margin-top: 5px;
        padding: 0.6em 0.8em 0.5em 0.8em;
        border-radius: 5px;
        border: 0.5px solid #ccc;
        background-color: #fff;
    }
</style>