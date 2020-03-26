<script>
  import Input from "./components/Input.svelte";
  let configInputText = {
    type: "number",
    id: "firstName",
    name: "firstName",
    placeholder: "first name",
    label: "First Name",
    hint: "There's a problem here.",
    min: 0,
    max: 24
  };
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
  main {
    margin: 4px;
    padding: 0px;
    border: 1px solid black;
  }
  .container {
    width: 100%;
    margin: 0;
    padding: 8px;
  }
</style>

<main>
  <div class="container">
    <h4>{value}&nbsp;</h4>

    <Input config={configInputText} bind:value />

  </div>
  <div class="alert-info">This is an info alert.</div>
  <div class="alert-success">This is a success alert.</div>
  <div class="alert-warning">This is a warning alert.</div>
  <div class="alert-error">This is an error alert.</div>
</main>
