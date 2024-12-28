<script lang="ts">
    let { children } = $props();
</script>

<div class="labelContainer">
    {@render children()}
</div>

<style>
    .labelContainer {
        background-image: url("/StickerLabel.svg");
        background-color: transparent;
        /* strech image to fill */
        background-size: 100% 100%;

        color: #835242;
        font-size: 50px;
        font-weight: 500;
        font-family: "Coiny", sans-serif;
        width: fit-content;
 

        line-height: 100%;
        padding:3rem;

        transform: rotate(-7deg);
    }
</style>
