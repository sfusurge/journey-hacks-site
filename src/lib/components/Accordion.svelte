<script lang="ts">
    let {question, answer} = $props();
    let isOpen = $state(false); 
    let innerHeight = $state(0);

    $inspect(innerHeight);
</script>

<div class="accordion">
    <button class="button" onclick={() => isOpen = !isOpen} >
      {question}
    </button>

    <div class="answer-container" style={`maxHeight: ${(isOpen? innerHeight : 0)}px`}> 
      <div class="answer" bind:clientHeight={innerHeight} class:closed={!isOpen} class:open={isOpen}>
        {answer}
      </div>
    </div> 
</div>
 
<style>
    .accordion {
        position: relative;
    }

    .answer-container {
        max-height: 0px;
        width: 100%;
        background-color: red;
        overflow: hidden;
        transition: max-height 0.2s ease-out;
    }

    .answer {
        position: absolute;
        width: 100%;
    }

    .closed {
        padding: 0 18px;
        background-color: white;
        max-height: 0;
        overflow: hidden;
    }

    .open {

    }
</style>

