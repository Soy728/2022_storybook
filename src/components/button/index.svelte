<script lang="ts">
   import './style.scss';
   export let label:string ='';
   export let size: "small" |"medium" | "large";
   export let variant: "none" |"contained" | "outlined";
   

</script>

<button class = "button" button-size={size} button-variant={variant}>
{label}</button>
