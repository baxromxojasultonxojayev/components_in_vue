<template>
  <dialog open>
    <slot></slot>
  </dialog>
</template>


<style scoped>
dialog {
  position: fixed;
  width: 50%;
  left: 30%;
  background: white;
  box-shadow: 1px 2px 9px rgb(161, 156, 156);
}
</style>