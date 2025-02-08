<script lang="ts">
    export let href: string;
    export let src: string;
    export let alt: string;
    export let width: string = "w-48";
    export let height: string = "h-auto";
</script>

<a href={href} target="_blank" rel="noopener noreferrer">
    <img src={src}
         alt={alt}
         class={`transition-transform duration-200 hover:scale-110 ${width} ${height}`}
    />
</a>
