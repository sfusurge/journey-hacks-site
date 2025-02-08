<script lang="ts">
    import StickyLabel from "../StickyLabel.svelte";
    import SponsorButton from "$lib/components/MainPageParts/SponsorButton.svelte";
</script>

<div class="pt-12">
    <div class="flex flex-col">
        <StickyLabel>
            Our Sponsors
        </StickyLabel>

        <div class="flex lg:flex-row flex-col items-center justify-center lg:gap-x-20 gap-y-10">
            <SponsorButton
                    href="https://www.perplexity.ai"
                    src="/sponsor-logos/perplexity-logo.svg"
                    alt="Perplexity Logo"
            />
            <SponsorButton
                    href="https://www.redbull.com/ca-en"
                    src="/sponsor-logos/redbull-logo.svg"
                    alt="Redbull Logo"
            />
            <SponsorButton
                    href="https://balsamiq.com/"
                    src="/sponsor-logos/balsamiq-logo.png"
                    alt="Balsamiq Logo"
            />
            <SponsorButton
                    href="https://www.caterdash.com/"
                    src="/sponsor-logos/caterdash-logo.svg"
                    alt="Caterdash Logo"
                    width="w-16"
                    height="h-16"
            />
        </div>
    </div>
</div>

<style></style>