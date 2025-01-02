<script lang="ts">
    import DesktopNav from "./DesktopNav.svelte";
    import MobileNav from "./MobileNav.svelte";

    let innerWidth = $state(0);

    const links = [
        ["About", "#"],
        ["FAQ", "#faq"],
        ["Our Team", "#our_team"],
        ["Countdown", "#countdown"],
    ];
</script>

<svelte:window bind:innerWidth />

{#if innerWidth < 560}
    <MobileNav {links}></MobileNav>
{:else}
    <DesktopNav {links}></DesktopNav>
{/if}
