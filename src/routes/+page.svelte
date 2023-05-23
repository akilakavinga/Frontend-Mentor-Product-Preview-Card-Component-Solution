<script>
    import ProductTile from "./ProductTile.svelte";
    import Attribution from "./Attribution.svelte";
    const product = {
        mobileSrc: "image-product-mobile.jpg",
        desktopSrc: "image-product-desktop.jpg",
        type: "perfume",
        name: "gabrielle essence Eau de parfum",
        description:
            "A floral, solar and voluptuous interpretation composed by Olivier Paige, Perfumer-Creator for the House of CHANEL.",
        price: 169.99,
        discount: 20,
    };
</script>

<main>
    <ProductTile {...product} />
    <Attribution />
</main>

<style lang="scss">
    @use "../styles/" as *;

    :global(*, *::after, *::before) {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    :global(body) {
        @include flexRow;
        height: 100vh;
        font-size: $bodyFz;
        font-family: $montserrat;
        background-color: $cream;
    }
</style>
