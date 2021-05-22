<template>
  <ul>
    <li v-for="goal in goals" :key="goal">
      <slot :item="goal" another-prop="bir nima"></slot>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      goals: ['Kursni tugatish', `Vue ni o'rganish`]
    }
  }
}
</script>