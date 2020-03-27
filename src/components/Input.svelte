<script>
  import { onMount } from "svelte";
  export let alt = "";
  export let autocomplete = "off";
  export let autofocus = "false";
  export let disabled = "false";
  export let hint = "There's a problem here.";
  export let id = "id";
  export let label = "label";
  export let max = undefined;
  export let maxlength = undefined;
  export let min = undefined;
  export let minlength = undefined;
  export let name = "name";
  export let placeholder = "placeholder";
  export let readonly = "false";
  export let regex = undefined;
  export let required = "false";
  export let type = "text"; // date, email, number, password, tel, text
  export let value = "";

  onMount(() => {
    const input = document.getElementById(id);
    if (autofocus === "true") {
      input.focus();
    }
    if (disabled === "true") {
      input.disabled = true;
    }
    if (readonly === "true") {
      input.readOnly = true;
    }
    if (required === "true") {
      input.required = true;
    }
  });

  function changeHandler(e) {
    value = e.target.value;
  }
  function inputHandler(e) {
    return true;
  }
</script>

<style>
  .input-group {
    margin: 0;
    padding: 8px;
    width: 100%;
    background-color: inherit;
  }
  .input-group > label {
    width: 100%;
    margin: 0;
    padding: 0;
    font-size: 80%;
    font-weight: 700;
    text-transform: uppercase;
    color: var(--theme-primary-700);
    background-color: inherit;
  }
  .input-group > input {
    --input-border: 1px;
    width: calc(100% - (2 * var(--input-border)));
    margin: 0;
    padding: 8px;
    outline: none;
    border: 1px solid var(--theme-neutral-200);
    border-radius: 4px;
  }
  .input-group > input:hover {
    outline: none;
    border-color: var(--theme-neutral-500);
  }
  .input-group > input:active,
  .input-group > input:focus {
    outline: none;
    border-color: var(--theme-neutral-500);
    box-shadow: 2px 2px 2px 1px var(--theme-neutral-100);
  }
  .input-group > input:invalid {
    outline: none;
    border: 1px solid var(--theme-alert-error-fg);
    box-shadow: none;
  }
  .input-group > input:invalid:active,
  .input-group > input:invalid:focus {
    outline: none;
    border: 1px solid var(--theme-alert-error-fg);
    box-shadow: 2px 2px 2px 1px var(--theme-neutral-100);
  }
  .input-hint {
    color: var(--theme-alert-error-fg);
    margin: 0;
    padding: 2px 0 0 0;
    font-size: 70%;
    font-weight: 700;
  }
</style>

<div class="input-group">
  <label for={id}>{label}</label>
  <input
    {alt}
    {autocomplete}
    {id}
    {name}
    {placeholder}
    {type}
    step="any"
    on:change|preventDefault={changeHandler}
    on:input|preventDefault={inputHandler}
    {value} />
  <div class="input-hint">{hint}&nbsp;</div>
</div>
