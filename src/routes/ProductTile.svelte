<script>
  import AddBtn from "./AddBtn.svelte";

  export let mobileSrc = "";
  export let desktopSrc = "";
  export let type = "";
  export let name = "";
  export let description = "";
  export let price = 0;
  export let discount = 0;
  const discPrice = price - discount;

  $: innerWidth = 0;
  $: isMobile = innerWidth <= 700;
</script>

<svelte:window bind:innerWidth />

<div class="tile">
  <div class="left">
    {#if isMobile}
      <img src={mobileSrc} alt="" />
    {:else}
      <img src={desktopSrc} alt="" />
    {/if}
  </div>
  <div class="right">
    <h3 class="type">{type}</h3>
    <h1 class="name">{name}</h1>
    <p class="description">{description}</p>
    <section class="priceSection">
      <h1 class="price">${discPrice}</h1>
      <span class="price2">${price}</span>
    </section>
    <AddBtn />
  </div>
</div>

<style lang="scss">
  @use "../styles" as *;

  .tile {
    display: grid;
    border-radius: 0.75rem;
    overflow: hidden;
    box-shadow: 10px 10px 20px rgba($color: $darkCream, $alpha: 0.2);
    @include mqPhone {
      grid-template-rows: 250px 1fr;
      max-width: 22.2rem;
    }
    @include mqDesktop {
      grid-template-columns: 300px 300px;
    }

    .left {
      // border: 1px solid red;

      img {
        max-width: 100%;
        width: 100%;
        display: block;
        object-fit: cover;
      }
    }

    .right {
      @include flexCol;
      align-items: flex-start;
      // border: 1px solid green;
      padding: 2rem;
      background: $white;
      max-width: 22.2rem;
      @include mqPhone {
        padding: 1.75rem;
      }

      .type {
        text-transform: uppercase;
        font-weight: 500;
        letter-spacing: 0.3rem;
        color: $darkGrayishBlue;
        font-size: 0.85rem;
      }

      .name {
        text-transform: capitalize;
        font-family: $fraunces;
        line-height: 1.75rem;
        color: $veryDarkBlue;
        font-size: 2rem;
        margin: 1.4rem 0;
        @include mqPhone {
          margin: 1rem 0;
        }
      }

      .description {
        color: $darkGrayishBlue;
        font-weight: 500;
        line-height: 1.5rem;
      }

      .priceSection {
        @include flexRow;
        justify-content: space-between;
        gap: 1.125rem;
        margin: 1.7rem 0;

        .price {
          font-family: $fraunces;
          font-size: 2rem;
          color: $darkCyan;
        }

        .price2 {
          text-decoration: line-through;
          color: $darkGrayishBlue;
        }
      }
    }
  }
</style>
