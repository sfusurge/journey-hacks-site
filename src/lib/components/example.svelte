<script lang="ts">
    // example a component

    // declare types for props
    interface Props {
        name: string;
        age: number;
        friends: string[];
        bleh: string; // some other data
    }

    // props are passed via "$props()"
    // use the spread syntax to set default and rename if needed
    let { name, age = 0, friends: friendsList, ...rest } = $props();

    let stuff = 123; // variables declared are not reactive, only run once during initialization (once client side, once server side, if ssr enabled)

    // use $state to declare reactive state (useEffect)
    let highlighted = $state(false);

    // use $derived to get a derived state (useMemo)
    let canDrive = $derived(age >= 16);

    // use $effect to do something when the states inside changes (useEffect)
    $effect(() => {
        console.log(`highlighted changed: ${highlighted}`);
    });

    // use $inspect to print to console whenever state inside changes
    $inspect(`highlighted changed ($inspect): ${highlighted}`);

    function toggleHighlight() {
        // state update is just variable assignment
        // this triggers rerender
        highlighted = !highlighted;
    }
</script>

<!-- declare "snippets" to reuse -->
{#snippet FriendLabel(name: string)}
    <div class="friend">
        {name}
    </div>
{/snippet}

<!-- Markup -->

<!-- use class:<css class name>=<boolean> to toggle css class based on a boolean -->
<div class="container" class:highlight={highlighted}>
    <!-- event functions same as React -->
    <div class="label" onclick={toggleHighlight}>
        <!-- template similar to react -->
        Name: {name}
    </div>

    <!-- inline function works too -->
    <div
        class="label"
        onclick={() => {
            console.log("bleh");
        }}
    >
        Age: {age}
    </div>

    <!-- use #if :elseif :else to do conditional render-->
    {#if canDrive}
        {name} can drive
    {:else if !canDrive}
        {name} cannot drive
    {:else}
        What???
    {/if}

    <!-- use #each to loop through a list -->
    Is friends with:
    {#each friendsList as friend, index}
        <label>{index}. {@render FriendLabel(friend)}</label>
    {/each}
</div>

<style>
    /* Css is scoped to this component only, and supports all selectors */

    .container {
        border: 2px solid red;
    }

    .highlight {
        border-color: blue;
    }
</style>
