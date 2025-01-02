<script lang="ts">
    import StickyLabel from "../StickyLabel.svelte";
    import Accordion from "../Accordion.svelte";

    type FAQ = {
        question: string;
        answer: string;
    };

    let FaqObjects: FAQ[] = [
        { question: "What is this event about?", answer: "This is an answer 0" },
        { question: "This is a question 1", answer: "This is an answer 1" },
        { question: "This is a question 2", answer: "This is an answer 2" },
        { question: "This is a question 3", answer: "This is an answer 3" },
        { question: "This is a question 4", answer: "This is an answer 4" },
        { question: "This is a question 5", answer: "This is an answer 5" },
        { question: "This is a question 6", answer: "This is an answer 6" },
    ];
</script>

<div id="faq">
    <div class="labelContainer"><StickyLabel>FAQ</StickyLabel></div>
    <div class="max-w-[960px] mx-auto grid md:grid-cols-2 gap-3 md:gap-8">
        <div class="flex flex-col gap-3">
            {#each FaqObjects.slice(0, Math.ceil(FaqObjects.length / 2)) as faq}
                <Accordion question={faq.question} answer={faq.answer} />
            {/each}
        </div>

        <div class="flex flex-col gap-3">
            {#each FaqObjects.slice(Math.ceil(FaqObjects.length / 2)) as faq}
                <Accordion question={faq.question} answer={faq.answer} />
            {/each}
        </div>
    </div>
</div>

<style>
    #faq {
        padding: 2rem;
        background-color: #dfb19b;
    }
</style>
