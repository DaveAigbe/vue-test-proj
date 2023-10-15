<script setup>
import ButtonElement from './components/ButtonElement.vue';
import CheckboxElement from './components/CheckboxElement.vue';
import GreetingBox from './components/GreetingBox.vue';
import RecipeItem from './components/RecipeItem.vue';
import { ref } from 'vue';

let count = 0;

const recipes = [
  {
    id: count++,
    title: "Baked Parmesan Pasta",
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [{name: "Cherry tomatoes", quantity: "5 oz"}, {name: "Pasta", quantity: "2oz"}]
  },
  {
    id: count++,
    title: "Crockpot Teriyaki Meatballs",
instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [{name: "Cherry tomatoes", quantity: "5 oz"}, {name: "Pasta", quantity: "2oz"}]
  },
  {
    id: count++,
    title: "Turkey Sloppy Joes",
instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [{name: "Cherry tomatoes", quantity: "5 oz"}, {name: "Pasta", quantity: "2oz"}]
  },
  {
    id: count++,
    title: "Pimento Cheesburger",
instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [{name: "Cherry tomatoes", quantity: "5 oz"}, {name: "Pasta", quantity: "2oz"}]
  },
  {
    id: count++,
    title: "Prime Rib Roast",
 instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [{name: "Cherry tomatoes", quantity: "5 oz"}, {name: "Pasta", quantity: "2oz"}]
  },
  {
    id: count++,
    title: "Blackened Salmon",
   instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [{name: "Cherry tomatoes", quantity: "5 oz"}, {name: "Pasta", quantity: "2oz"}]
  },
 
]

const recipeFontSize = ref(12)
const buttonText = ref('')
const isChecked = ref(false)

function updateIsChecked(v) {
  isChecked.value = v
}

</script>

<template>
  <main>
    <GreetingBox>Im starting to get the hang of things!</GreetingBox>
    <div>
      <CheckboxElement :is-checked="isChecked" @update-is-checked="(v) => updateIsChecked(v)" />
      <div v-if="isChecked" style="color: green; padding: 4px; background-color:white;">
        Checkbox Active
      </div>
    </div>
    <div :style="{fontSize: recipeFontSize + 'px'}">
      <RecipeItem v-for="item in recipes" v-bind="item"  :key="item.id" @enlarge-text="(n) => recipeFontSize += n" @reduce-text="(n) => recipeFontSize -= n"/>
    </div>

    <!-- <input v-model="buttonText"> -->
    <!-- <ButtonElement :title="buttonText"/> -->
  </main>
</template>

<style scoped>
</style>
