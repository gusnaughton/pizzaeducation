<script>
    import "carbon-components-svelte/css/white.css";
    import { Button, TextInput, TextArea } from "carbon-components-svelte";

    export let stepObj;

    function populateValue(evt, field) {
      stepObj = {
        ...stepObj,
        [field]: evt.target.value,
      }
      console.log(stepObj);
    }

  </script>
  
  
  <div class="app">  
    <h2>Step {JSON.stringify(stepObj)}</h2>
    <div class="recipe-addition-section">
      <TextInput on:change={(evt) => populateValue(evt, "action")} labelText="Action/Tool" placeholder="Enter action..." />
      <TextInput on:change={(evt) => populateValue(evt, "name")} labelText="Ingredient Name" placeholder="Enter ingredient name..." />
      <TextInput on:change={(evt) => populateValue(evt, "quantity")} labelText="Quantity" placeholder="Enter quantity..." />
      <TextInput on:change={(evt) => populateValue(evt, "unit")} labelText="Quantity" placeholder="Enter quantity..." />
      <TextInput on:change={(evt) => populateValue(evt, "duration")} labelText="Duration" placeholder="Enter duration..." />
      <TextArea on:change={(evt) => populateValue(evt, "description")} labelText="Step description" placeholder="Enter a description..." />
    </div>
  
  </div>
  
  