<script>
  export let alt = "";
  export let autocomplete = "off";
  export let autofocus = "";
  export let disabled = "";
  export let id = "id";
  export let max = undefined;
  export let maxlength = undefined;
  export let min = undefined;
  export let minlength = undefined;
  export let name = undefined;
  export let placeholder = "placeholder";
  export let readonly = false;
  export let required = false;
  export let step = undefined;
  export let type = "text"; // date, email, number, password, tel, text
  export let value = "";

  function handler(e) {
    value = e.target.value;
  }
</script>

<style>

</style>

<div class="input-group">
  <label for={config.id}>{config.label}</label>
  <input {alt} {autocomplete} on:change|preventDefault={handler} {value} />
  <div class="input-hint">{config.hint}&nbsp;</div>
</div>
