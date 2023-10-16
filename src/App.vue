<script setup>
// import ButtonElement from './components/ButtonElement.vue';
import CheckboxElement from './components/CheckboxElement.vue'
import ComputedCustomInput from './components/ComputedCustomInput.vue'
import CustomInput from './components/CustomInput.vue'
import DynamicList from './components/DynamicList.vue'
import FancyButton from './components/FancyButton.vue'
import GreetingBox from './components/GreetingBox.vue'
import LoginBox from './components/LoginBox.vue'
import RecipeItem from './components/RecipeItem.vue'
import CardBase from './components/CardBase.vue'
import { ref } from 'vue'

let count = 0

const recipes = [
  {
    id: count++,
    title: 'Baked Parmesan Pasta',
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [
      { name: 'Cherry tomatoes', quantity: '5 oz' },
      { name: 'Pasta', quantity: '2oz' }
    ]
  },
  {
    id: count++,
    title: 'Crockpot Teriyaki Meatballs',
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [
      { name: 'Cherry tomatoes', quantity: '5 oz' },
      { name: 'Pasta', quantity: '2oz' }
    ]
  },
  {
    id: count++,
    title: 'Turkey Sloppy Joes',
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [
      { name: 'Cherry tomatoes', quantity: '5 oz' },
      { name: 'Pasta', quantity: '2oz' }
    ]
  },
  {
    id: count++,
    title: 'Pimento Cheesburger',
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [
      { name: 'Cherry tomatoes', quantity: '5 oz' },
      { name: 'Pasta', quantity: '2oz' }
    ]
  },
  {
    id: count++,
    title: 'Prime Rib Roast',
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [
      { name: 'Cherry tomatoes', quantity: '5 oz' },
      { name: 'Pasta', quantity: '2oz' }
    ]
  },
  {
    id: count++,
    title: 'Blackened Salmon',
    instructions: `
    Toss the cherry tomatoes in the oil and add the parmesan cheese.
    Bake until the tomatoes are roasted.
    Cook the pasta and drain, reserving some cooking water.
    Remove the tomatoes from the oven, add the garlic and stir everything together.
    Add the pasta and toss to coat in the sauce.
  `,
    ingredients: [
      { name: 'Cherry tomatoes', quantity: '5 oz' },
      { name: 'Pasta', quantity: '2oz' }
    ]
  }
]

const fruits = [
  'apple',
  'orange',
  'grape',
  'melon',
  'pineapple',
  'guava',
  'tamarind',
  'pomegranate',
  'lemon'
]

const recipeFontSize = ref(12)
// const buttonText = ref('')
const isChecked = ref(false)
const searchText = ref('')
const username = ref('')
const password = ref('')

function updateIsChecked(v) {
  isChecked.value = v
}

function loginValid() {
  return username.value === 'admin' && password.value === '123qwe'
}
</script>

<template>
  <main>
    <GreetingBox>Im starting to get the hang of things!</GreetingBox>
    <!-- Sep -->
    <div>
      <CheckboxElement :is-checked="isChecked" @update-is-checked="(v) => updateIsChecked(v)" />
      <div v-if="isChecked" style="color: green; padding: 4px; background-color: white">
        Checkbox Active
      </div>
    </div>
    <!-- Sep -->
    <div>
      <DynamicList :list-values="fruits" />
    </div>
    <!-- Sep -->
    <CustomInput v-model="searchText" />
    <br />
    <ComputedCustomInput v-model="searchText" />
    <div style="color: red">
      {{ searchText }}
    </div>
    <!-- Sep -->
    <LoginBox v-model:username="username" v-model:password="password" />
    <button style="margin-bottom: 5px" @click="() => console.log(loginValid())">Check login</button>
    <!-- Sep -->
    <br />
    <FancyButton>3:47am</FancyButton>
    <CardBase>
      <template #header>
        <h2>Header</h2>
      </template>
      <template #content>
        <p>Some content</p>
      </template>
      <template #footer>
        <h4>Footer</h4>
      </template>
    </CardBase>
    <!-- Sep -->
    <div :style="{ fontSize: recipeFontSize + 'px' }">
      <RecipeItem
        v-for="item in recipes"
        v-bind="item"
        :key="item.id"
        @enlarge-text="(n) => (recipeFontSize += n)"
        @reduce-text="(n) => (recipeFontSize -= n)"
      />
    </div>

    <!-- <input v-model="buttonText"> -->
    <!-- <ButtonElement :title="buttonText"/> -->
  </main>
</template>

<style scoped></style>
