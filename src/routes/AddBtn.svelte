<script>
    let src = "images/icon-cart.svg";
</script>

<button>
    <img src="icon-cart.svg" alt="cart icon" />
    <span>Add to Cart</span>
</button>

<style lang="scss">
    @use "../styles" as *;

    button {
        @include flexRow;
        gap: 0.6rem;
        border: none;
        width: 100%;
        color: white;
        background: $darkCyan;
        font-family: $montserrat;
        font-weight: 700;
        font-size: 0.95rem;
        padding: 1rem 0;
        border-radius: 0.5rem;
        cursor: pointer;
        transition: background-color 75ms;

        &:hover {
            background-color: $darkGreen;
        }
    }
</style>
