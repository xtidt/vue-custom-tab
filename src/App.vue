<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />

    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="用户管理" name="first">用户管理</el-tab-pane>
      <el-tab-pane label="配置管理" name="second">配置管理</el-tab-pane>
      <el-tab-pane label="角色管理" name="third">角色管理</el-tab-pane>
      <el-tab-pane label="定时任务补偿" name="fourth">定时任务补偿</el-tab-pane>
    </el-tabs>

    <hr>

    <Tabs v-model="activeName" @tab-click="handleClick">
      <Panel label="用户管理" name="first">用户管理</Panel>
      <Panel label="配置管理" name="second">配置管理</Panel>
      <Panel label="角色管理" name="third">角色管理</Panel>
      <Panel label="定时任务补偿" name="fourth">定时任务补偿</Panel>
    </Tabs>
  </div>
</template>

<script>
import Tabs from './components/Tabs'
import Panel from './components/Panel'

export default {
  name: 'App',

  data () {
    return {
      activeName: 'third'
    }
  },

  components: {
    Tabs,
    Panel
  },

  methods: {
    handleClick (tab, event) {
      console.log(tab, event)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
