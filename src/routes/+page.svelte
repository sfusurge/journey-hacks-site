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
</script>

<Nav></Nav>
<Home />
<Apply />
<About />
<Faq />
<InfoBook />
<Counter />
<ConveyorBelt />
<Footer />
