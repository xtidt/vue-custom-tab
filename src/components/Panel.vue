<template>
  <div v-show="name === $parent.value">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Panel',
  props: ['name'],
  data () {
    return {}
  },
  mounted () {
  }
}
</script>
