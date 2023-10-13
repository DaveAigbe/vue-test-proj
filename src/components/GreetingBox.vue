<template>
  <div class="greeting-box">
    <strong>Welcome!</strong>
    <br/>
    <slot />
  </div>
</template>

<style scoped>
.greeting-box {
  color: #666;
  border: 1px solid green;
  border-radius: 4px;
  padding: 20px;
  background-color: #f8f8f8;
}

  
strong {
	color: green;    
}
</style>