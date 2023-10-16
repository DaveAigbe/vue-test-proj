<template>
  <div class="container">
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <slot name="content"></slot>
    </main>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script setup></script>

<style scoped>
.container {
  background-color: white;
  color: black;
  border-radius: 4px;
  margin-top: 10px;
  width: 50%;
  padding: 20px;
}
</style>
