<script lang="ts">
  import Example from "$lib/components/example.svelte";
  import Home from "$lib/components/MainPageParts/home.svelte";
  import Apply from "$lib/components/MainPageParts/apply.svelte";
  import About from "$lib/components/MainPageParts/about.svelte";
  import Faq from "$lib/components/MainPageParts/faq.svelte";
  import InfoBook from "$lib/components/MainPageParts/InfoBook.svelte";
  import Footer from "$lib/components/Footer.svelte";
  import ConveyorBelt from "$lib/components/MainPageParts/ConveyorBelt/conveyorBelt.svelte";
  import Counter from "$lib/components/MainPageParts/counter.svelte";
  import Nav from "$lib/components/Nav/Nav.svelte";

  let scrollY = $state(0);
  let isTop = $derived(scrollY < 300);
  $effect(() => {
    if (isTop) {
      document.body.style.setProperty("background-color", "#C4D086");
    } else {
      document.body.style.setProperty("background-color", "#57392E");
    }
  });
</script>

<svelte:window bind:scrollY />

<Nav></Nav>
<Home />
<Apply />
<About />
<Faq />
<InfoBook />
<Counter />
<ConveyorBelt />
<Footer />
