<script lang="ts">
  export let title: string;
  export let subtitle: string | null = null;
</script>

<section class="root">
  {#if subtitle}
    <span>
      <h2 class="root__title">{title}</h2>
      <div>{subtitle}</div>
    </span>
  {:else}
    <h2 class="root__title">{title}</h2>
  {/if}
  <div class="content">
    <slot />
  </div>
</section>

<style>
  .root {
    display: grid;
    font-family: var(--font-family-code);
    color: var(--color-main-text);
    justify-items: left;
  }

  .root__title {
    font-weight: 300;
  }

  .root span {
    display: flex;
    align-items: baseline;
    gap: 0.5rem;
  }

  .root span div {
    color: var(--color-alt-text);
    font-size: small;
  }

  .content {
    width: 100%;
    margin-top: 1rem;
    font-weight: 300;
  }
</style>
