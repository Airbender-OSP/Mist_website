<script>
import { onMount } from 'svelte';
import {MDCRipple} from '@material/ripple';

onMount(() => {
  const buttonRipple = new MDCRipple(document.getElementById(id));
});

export let id;
export let text;
export let onClickFunction;
</script>


<button class="mdc-button mdc-button--raised mdc-button--leading" {id} on:click={onClickFunction}>
  <span class="mdc-button__ripple"></span>
  <i class="material-icons mdc-button__icon" aria-hidden="true"
    >icon</i
  >
  <span class="mdc-button__label">{text}</span>
</button>
