<script lang="ts">
    import StickyLabel from "../StickyLabel.svelte";
    import Accordion from "../Accordion.svelte";
</script>

<div id="faq">
    <div class="labelContainer"> <StickyLabel>FAQ</StickyLabel></div>
    <div class="max-w-[960px] mx-auto grid grid-cols-2 gap-12">
        <div class="bg-neutral-300"><Accordion question="This is a question" answer="This is an answer"></Accordion></div>
        <div class="bg-white">Hello</div>
    </div>
</div>

<style>
    #faq {
        padding: 2rem;
        background-color: #dfb19b;
    }
</style>