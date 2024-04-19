

<style lang="scss">
    @use "$lib/scss/variables" as app;

    main#home {
        min-height: calc(100vh - 10rem);
        overflow: hidden;

    }

    h1 {
        margin-top: 10rem;
        color: app.$color-brand;
    }
</style>

<script lang="ts">
    import Hero from "../lib/sections/hero.svelte";
    import About from "../lib/sections/about.svelte";
    import Services from "../lib/sections/services.svelte";
    import Prices from "../lib/sections/prices.svelte";
    import Footer from "../lib/widgets/Footer.svelte";

</script>

<main id="home">
    <Hero/>
    <About/>
    <Services/>
    <Prices/>
    <Footer/>

</main>


