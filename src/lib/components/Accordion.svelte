<script lang="ts">
    let { question, answer } = $props();
    let isOpen = $state(false);
    let innerHeight = $state(0);
</script>

<div class="accordion">
    <button class="button" onclick={() => (isOpen = !isOpen)}>
        {question}
    </button>

    <div class="answer-container" style="height:{innerHeight}px; max-height: {isOpen ? innerHeight : 0}px;">
        <div class="answer" bind:clientHeight={innerHeight}>
            {answer}
        </div>
    </div>
</div>

<style>
    .accordion {
        height: fit-content;
    }

    .answer-container {
        position: relative;
        width: 100%;
        background-color: red;
        transition: max-height 0.2s ease-out;
        overflow: hidden;
        max-height: 0px;
    }

    .answer {
        position: absolute;
        width: 100%;
        left:0;
        top: 0;
    }
</style>
