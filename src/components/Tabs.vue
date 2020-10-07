<template>
  <div class="tabs-wrapper">
    <div class="tabs-header">
      <button
        v-for="(item, index) in tabPanes"
        :key="index"
        class="btn"
        :class="{ active: item.name === activeName }"
        @click="handleTabClick(item)"
      >
        {{ item.$attrs.label }}
      </button>
    </div>
    <div class="tabs-body">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['value'],
  name: 'Tabs',
  data () {
    return {
      tabPanes: []
    }
  },
  computed: {
    activeName () {
      return this.value
    }
  },
  methods: {
    handleTabClick (tab) {
      this.$emit('input', tab.name)
    }
  },
  mounted () {
    this.tabPanes = this.$children
  }
}
</script>

<style lang="less">
.tabs {
  &-header {
    border-bottom: 1px solid gray;
  }
}
.btn {
  background: none;
  padding: 5px 10px;
  border: none;
  margin-bottom: 5px;
  outline: none;
  cursor: pointer;
}
.active {
  background: #409EFF;
  color: #fff;
}
</style>
