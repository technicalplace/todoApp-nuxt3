<template>
  <div>
    <header>Todo Card App</header>
    <slot />
  </div>
</template>

<style scoped>
header{
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  background-color: #96a572;
  width: calc(100% - 100px);
  height: 54px;
  font-size: 4rem;
  border-radius: 16px;
}
</style>