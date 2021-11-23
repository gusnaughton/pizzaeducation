<script>
    import "carbon-components-svelte/css/white.css";
    import { Button, TextInput, TextArea } from "carbon-components-svelte";

    export let ingredientObj

    function populateValue(evt, field) {
      ingredientObj = {
        ...ingredientObj,
        [field]: evt.target.value,
      }
      console.log(ingredientObj);
    }
  </script>
  
  
  <div class="app">  
    <h2>Ingredient {JSON.stringify(ingredientObj)}</h2>
    <div class="recipe-addition-section">
      <TextInput on:change={(evt) => populateValue(evt, "name")} labelText="Ingredient Name" placeholder="Enter ingredient name..." />
      <TextInput on:change={(evt) => populateValue(evt, "quantity")} labelText="Quantity" placeholder="Enter quantity..." />
      <TextInput on:change={(evt) => populateValue(evt, "unit")} labelText="Unit" placeholder="Enter unit..." />
    </div>
  
  </div>
  
  