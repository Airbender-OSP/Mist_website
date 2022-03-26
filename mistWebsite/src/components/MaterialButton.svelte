<script>
  import { onMount } from 'svelte';
  import { MDCRipple } from '@material/ripple';

  onMount(() => {
    const buttonRipple = new MDCRipple(document.getElementById(id));
  });

  export let id;
  export let text;
  export let onClickFunction;
  export let icon;
</script>

<button
  style="background-color: #f6f6f6; color: #9d9d9d"
  class="mdc-button mdc-button--raised mdc-button--leading"
  {id}
  on:click={onClickFunction}
>
  <span class="mdc-button__ripple" />
  <img
    class="material-icons mdc-button__icon"
    aria-hidden="true"
    src={icon}
    alt="img"
    border-radius="20%"
  />
  <span class="mdc-button__label">{text}</span>
</button>

<style>
  /* .mdc-button mdc-button--raised mdc-button--leading {
    background-color: #f6f6f6;
  } */
</style>
