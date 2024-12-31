<script lang="ts">
  import { getAllContexts } from "svelte";

  const links = [
    ["About", "#"],
    ["FAQ", "#"],
    ["Our Team", "#"],
    ["Countdown", "#"],
  ];

  let defaultNav: string = "bg-[#c4d086] top-0 max-w-[100vw]";
  let dockedNav: string =
    "bg-[#57392E] max-w-[1200px] md:top-6 md:rounded-lg dockedNav";

  let scrollY = $state(0);
  $inspect(scrollY);
</script>

<svelte:window bind:scrollY />

<nav
  class={`flex fixed inset-x-0 mx-auto p-4 z-[999] items-center w-full justify-between ${scrollY <= 720 ? defaultNav : dockedNav}`}
>
  <div class="flex gap-6 items-center text-lg font-medium">
    <a
      href="#"
      class={`${scrollY <= 720 ? "bg-[#57392E] hover:bg-[#57392E] text-white" : "bg-[#c4d086] text-[#57392E]"} block  w-fit px-4 py-2 rounded-md`}
      >Apply</a
    >

    <div class="flex gap-6 -ml-1">
      {#each links as [name, url]}
        <a
          href={url}
          class={`${
            scrollY <= 720
              ? "hover:underline text-[#57392E] decoration-[1.5px] decoration-wavy no-underline"
              : "text-white"
          }`}>{name}</a
        >
      {/each}
    </div>
  </div>

  <a
    href="#"
    class="w-10 h-10 flex items-center text-center"
    aria-label="SFU Surge"
  >
    <svg
      width="30"
      height="31"
      class="h-8 mx-auto"
      viewBox="0 0 30 31"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        fill-rule="evenodd"
        clip-rule="evenodd"
        d="M14.9695 30.9268C23.2369 30.9268 29.939 24.2247 29.939 15.9573C29.939 7.68986 23.2369 0.987793 14.9695 0.987793C6.70207 0.987793 0 7.68986 0 15.9573C0 24.2247 6.70207 30.9268 14.9695 30.9268ZM10.6408 17.0278L15.8901 3.58291L19.9408 10.4885L14.8445 14.066L17.3959 17.2498L19.9471 20.4338L11.83 26.657L14.2999 18.3678L10.6408 17.0278Z"
        fill={`${scrollY <= 720 ? "#57392E" : "#FFFFFF"}`}
      />
    </svg>
  </a>

  <style>
    nav {
      transition-property: all;
      transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
      transition-duration: 300ms;
    }
  </style>
</nav>
