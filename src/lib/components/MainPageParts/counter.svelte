<script>
    import { onMount } from "svelte";
    import { SvelteDate } from "svelte/reactivity";

    const hackathonDate = new Date(2025, 1, 18, 11, 15, 0);
    let nowDate = $state(new Date());

    let difference = $derived(new Date(Math.max(0, hackathonDate.getTime() - nowDate.getTime())));

    const msInDay = 1000 * 60 * 60 * 24;
    const msInHours = 1000 * 60 * 60;
    const msInMinute = 1000 * 60;

    let days = $derived(new String(Math.floor(difference.getTime() / msInDay)).padStart(2, "0"));
    let hours = $derived(new String(Math.floor((difference.getTime() % msInDay) / msInHours)).padStart(2, "0"));
    let minutes = $derived(new String(Math.floor((difference.getTime() % msInHours) / msInMinute)).padStart(2, "0"));

    $inspect(days);
    $inspect("hours: " + hours);
    $inspect("minutes: " + minutes);

    onMount(() => {
        setInterval(() => {
            nowDate = new Date();
        }, 1000);
    });
</script>

<div id="countdown" class="relative w-full h-full max-w-[100vw] -mt-[1px] pointer-events-none select-none">
    <img alt="ceiling" src="/counter/ceiling.webp" class="relative w-full h-auto hidden md:block" />

    <img alt="ceiling" src="/counter/ceiling-mobile.webp" class="relative w-full h-auto block md:hidden" />

    <div class="absolute top-0 left-0 w-full h-full">
        <img
            alt="foreground"
            src="/counter/counter.webp"
            class="relative w-[93.75%] h-auto md:h-[83.149%] md:w-auto top-[9.5304%] z-30 mx-auto"
        />
    </div>

    <div class="absolute top-0 left-0 w-full h-full">
        <div
            class="relative z-40 left-[3.125%] w-[27%] md:w-[12.8732344001%] h-[28.05437%] md:left-[27.6506%] top-[54.552552%] flex items-center"
        >
            <div class="font-coiny text-[12vw] md:text-[6vw] text-center w-[2ch] block mx-auto" id="seconds-digit-1">
                {days}
            </div>
        </div>

        <div
            class="absolute z-40 left-[36.10625%] w-[27%] md:w-[12.8732344001%] h-[28.05437%] md:left-[43.3756%] top-[54.552552%] flex items-center"
        >
            <div class="font-coiny text-[12vw] md:text-[6vw] text-center w-[2ch] block mx-auto" id="seconds-digit-1">
                {hours}
            </div>
        </div>

        <div
            class="absolute z-40 left-[69.115625%] w-[27%] md:w-[12.8732344001%] h-[28.05437%] md:left-[59.11407%] top-[54.552552%] flex items-center"
        >
            <div class="font-coiny text-[12vw] md:text-[6vw] text-center w-[2ch] block mx-auto" id="seconds-digit-1">
                {minutes}
            </div>
        </div>
    </div>
</div>

<style>
    .font-coiny {
        font-family: "Coiny";
        font-kerning: none;
        color: #57392e;
    }
</style>
