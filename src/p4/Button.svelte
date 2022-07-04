<script>
  import {ACCENT_COLOR} from '../packager/brand';
  export let secondary;
  export let dangerous;
  export let text;

  const getColor = () => {
    if (secondary) return '#0FBD8C';
    if (dangerous) return '#FF8C1A';
    return ACCENT_COLOR;
  };
</script>

<style>
  
  .text {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    z-index: 10;
  }
  /* Because we want color to be settable from brand.js, it becomes complicated to make it dim while active */
  .dimmer {
    display: none;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.25);
  }
  
</style>

<button on:click class="mdui-btn mdui-color-pink-accent mdui-ripple">
  {text}
</button>
