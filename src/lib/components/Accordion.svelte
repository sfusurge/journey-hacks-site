<script lang="ts">
  interface Props {
    question: string;
    answer: string;
  }

  let { question, answer } = $props();

  let isOpen = $state(false);
  let innerHeight = $state(0);
</script>

<div class="accordion">
  <button
    class="button flex flex-row content-between w-full font-bold tracking-wide"
    onclick={() => (isOpen = !isOpen)}
  >
    <div class="w-full text-left">{question}</div>

    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="size-6 self-end"
      style="transform: rotate({isOpen
        ? 180
        : 0}deg); transition: transform 0.2s ease;"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="m19.5 8.25-7.5 7.5-7.5-7.5"
      />
    </svg>
  </button>

  <div
    class="answer-container"
    style="height:{innerHeight}px; max-height: {isOpen ? innerHeight : 0}px;"
  >
    <div class="answer" bind:clientHeight={innerHeight}>
      {answer}
    </div>
  </div>
</div>

<style>
  .accordion {
    height: fit-content;
    background-color: #8f6455;
    border-radius: 4px;
    color: white;
    padding: 0.75em;
  }

  .answer-container {
    position: relative;
    width: 100%;
    transition: max-height 0.2s ease-out;
    overflow: hidden;
    max-height: 0px;
  }

  .answer {
    position: absolute;
    padding-top: 0.25rem;
    width: 100%;
    left: 0;
    top: 0;
  }
</style>
