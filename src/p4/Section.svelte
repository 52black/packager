<script>
  import ResetButton from './ResetButton.svelte';

  export let caption = false;
  export let center = false;
  export let modal = false;
  export let accent = '';
  export let reset;
</script>

<style>
  .card {
    max-width: 625px;
    margin: auto;
    border-radius: 0.3em;
    background-color: #fff;
    padding: 1em;
    margin-top: 1em;
    margin-bottom: 1em;
    -webkit-box-shadow: 0 7px 8px -4px rgba(0, 0, 0, 0.03), 0 12px 17px 2px rgba(0, 0, 0, 0.021), 0 5px 22px 4px rgba(0, 0, 0, 0.018) !important;
    box-shadow: 0 7px 8px -4px rgba(0, 0, 0, 0.03), 0 12px 17px 2px rgba(0, 0, 0, 0.021), 0 5px 22px 4px rgba(0, 0, 0, 0.018) !important;
  }
  :global([theme="dark"]) .card {
    background: #222;
  }
  .caption {
    font-style: italic;
  }
  .modal {
    width: 100%;
    max-width: 400px;
    margin: 0 8px;
  }
  .center {
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .reset {
    float: right;
  }
</style>

<div
  class="card"
  class:caption
  class:modal
  class:center={caption || center}
  style:border-top={accent ? `6px solid ${accent}` : ''}
>
  {#if reset}
    <div class="reset">
      <ResetButton on:click={reset} />
    </div>
  {/if}
  <slot></slot>
</div>
