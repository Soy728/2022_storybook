<script lang="ts">
  import './button.css';
  import { createEventDispatcher } from 'svelte';
  /**
   * Is this the principal call to action on the page?
   */
  export let primary = false;

  /**
   * What background color to use
   */
  export let backgroundColor;
  /**
   * How large should the button be?
   */
  export let size = 'medium';
  /**
   * Button contents
   */
  export let label = '';
  export let variant;

  let mode = primary ? 'storybook-button--primary' : 'storybook-button--secondary';

  let bgc = backgroundColor ? `background-color: ${backgroundColor}` : '';
  let style = variant; 
  const dispatch = createEventDispatcher();

  /**
   * Optional click handler
   */
  function onClick(event) {
    dispatch('click', event);
  }
</script>

<button
  type="button"
  class={['storybook-button', `storybook-button--${size}`, mode].join(' ')}
  {bgc}
  on:click={onClick}>
  {label}
</button>
