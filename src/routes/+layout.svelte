<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<svelte:head>
	<!-- to preload font and image to be used in front page -->
	<link rel="preload" href="/bg.webp" as="image" />
	<link rel="preload" href="/fonts/coiny.woff2" type="font/woff2" as="font" crossorigin="anonymous"/>
	<link rel="preload" href="/fonts/neue_medium.woff" type="font/woff" as="font" crossorigin="anonymous"/>

	<title>Journey Hacks 2025</title>
	<meta name="description" content="Journey Hacks 2025, hosted by SFU Surge"/>

	<meta property="og:title" content="Journey Hacks 2025"/>	
	<meta property="og:description" content="JOURNEY HACKS JOURNEY HACK JOURNEY HACKS"/>	
	<meta property="og:image" content="/bg.webp"/>	
	<meta property="og:type" content="website"/>	
	<meta property="og:url" content="https://preview--journeyhacks.netlify.app/"/>	


</svelte:head>

{@render children()}
