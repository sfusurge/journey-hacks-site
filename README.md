# Journey-hacks-site
Static site development for Journey hacks 2025.

## Useful resources
* [Figma designs](https://www.figma.com/design/2c0neayYTzaNd4gWoRHRms/JourneyHacks-2025?node-id=66-2&p=f&t=mwEcRce7zsrZ5S9o-0)
* [Vector assets exports (from figma)](https://drive.google.com/drive/folders/1I1xPximLWm2oZPk4VxsPAUVFpM_wQuz5?usp=sharing)
    + note that *.svg files downloaded may need to be minimized before use
    + [this](https://github.com/svg/svgo) seems like a good choice to do so
* [Svelte docs](https://svelte.dev/docs/svelte/overview)
    + alternatively, just dm @goldentoaste for help :P
    + we are not anticipating many framework specific code for this static site.

## Project structure

#### Global styles
* All global style/css should go in `src/app.css`, it will be shared amongst all component/pages
* styles for a particular component can either be done in tailwind, or in `<style> </style>` tag of the component itself.

#### Main page
* `src/routes/+page.svelte`
* This site will only have a single page, which we will implement the sections of it in their own components
* Each section of the page should have an id such that user can jump to a section with `<a href="#sectionName"/>`.

#### Components
* `src/lib/components`
* see `src/lib/components/example.svelte` for basic examples of a svelte component
* Each `.svelte` file is a component, which contains all the script, template, and style this component has.
* Components in the lib folder are setup to be imported with `import CompName from "$lib/components/CompName.svelte`
* Usage of components, ie, passing props to it is similar to React.

#### Static assets
* `static/...`
* All static assets, such as fonts, svgs or other images goes in the static folder.
* Assets in `static` can be referenced by "/foldername/filename", for example if there is a `static/icons/plus.svg`, then in any `.svelte` file, you can do:
```html
<img src="/icons/plus.svg" alt="plus icon"/>
```

## Workflow