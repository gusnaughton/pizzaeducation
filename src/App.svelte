<script>
  import "carbon-components-svelte/css/white.css";
  import { Button, TextInput, TextArea } from "carbon-components-svelte";
  import Step from "./Step.svelte"
  import Ingredient from "./Ingredient.svelte"

  let ingredients = [];
  let steps = [];
  let name = "";
  let servings = "";
  let calories = "";
  let description = "";

  function handleSubmit() {
    console.log({
      ingredients,
      steps,
      name,
      servings,
      calories,
      description
    })
  }

  function addIngredient() {
    console.log("fuck");
    ingredients = [...ingredients, {
      name: "",
      quantity: "",
      unit: "",
    }]
  }

  function addStep() {
    console.log("step");
    steps = [...steps, {
      action: "",
      name: "",
      quantity: "",
      unit: "",
      duration: "",
      description: "",
    }]
  }

</script>


<div class="app">

  <h1>Add a recipe</h1>

  <h2>Recipe Metadata</h2>
  <div class="recipe-addition-section">
    <TextInput bind:value={name} labelText="Recipe Name" placeholder="Enter recipe name..." />
    <TextInput bind:value={servings} labelText="Servings" placeholder="Enter servings..." />
    <TextInput bind:value={calories} labelText="Calories" placeholder="Enter calories..." />
    <TextArea bind:value={description} labelText="App description" placeholder="Enter a description..." />

    {#each ingredients as ingredient, idx}
    <Ingredient bind:ingredientObj={ingredient[idx]}></Ingredient>
    {/each}
    <Button on:click={addIngredient}>Add Ingredient</Button>
    

    {#each steps as step,idx}
    <Step bind:stepObj={steps[idx]}></Step>
    {/each}
    <Button on:click={addStep}>Add Step</Button>
  </div>

  <Button on:click={handleSubmit}>Submit</Button>
</div>

