<script>
    export let funcToUse;
    export let buttonText = "Template button text";
</script>

<main>
    <button on:click={funcToUse}>
        <p>{buttonText}</p>
    </button>
</main>
