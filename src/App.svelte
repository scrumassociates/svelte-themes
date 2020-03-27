<script>
  import Input from "./components/Input.svelte";
  let value = "Alvin";
</script>

<style>
  h1 {
    color: var(--theme-alert-info-fg);
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  .alert-info,
  .alert-success,
  .alert-warning,
  .alert-error {
    --margin: 8px;
    --padding: 24px;
    border: 0;
    border-radius: 4px;
    width: calc(100%- (2 * var(--margin)));
    margin: var(--margin);
    padding: var(--padding);
  }
  .alert-info {
    color: var(--theme-alert-info-fg);
    background-color: var(--theme-alert-info-bg);
  }
  .alert-success {
    color: var(--theme-alert-success-fg);
    background-color: var(--theme-alert-success-bg);
  }
  .alert-warning {
    color: var(--theme-alert-warning-fg);
    background-color: var(--theme-alert-warning-bg);
  }
  .alert-error {
    color: var(--theme-alert-error-fg);
    background-color: var(--theme-alert-error-bg);
  }
  .container {
    --container-margin: 0px;
    --container-padding: 8px;
    width: calc(100%- (2 * var(--container-margin)));
    margin: var(--container-margin);
    padding: 24px;
  }
</style>

<!-- export let alt = "";
  export let autocomplete = "off";
  export let autofocus = "";
  export let disabled = "";
  export let hint = "There's a problem here.";
  export let id = "id";
  export let label = "label";
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
  export let value = ""; -->

<div class="container">
  <h4>{value}&nbsp;</h4>

  <Input
    alt="Enter first name"
    autofocus="false"
    hint="Enter first name"
    id="firstName"
    label="First Name"
    maxlength="10"
    name="firstName"
    placeholder="first name"
    type="email"
    disabled="false"
    readonly="false"
    required="true"
    bind:value />

</div>
<!-- <div class="alert-info">This is an info alert.</div>
  <div class="alert-success">This is a success alert.</div>
  <div class="alert-warning">This is a warning alert.</div>
  <div class="alert-error">This is an error alert.</div> -->
