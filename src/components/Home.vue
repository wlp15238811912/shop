<template>
  <div>
    <el-button type="info" @click="logout">退出</el-button>
    <el-tree :data="data" show-checkbox  node-key="id" ref="tree" highlight-current
      :props="defaultProps">
    </el-tree>
    <el-button @click="getCheckedNodes">通过 node 获取</el-button>


  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [{
        id: 1,
        label: '一级 1',
        children: [{
          id: 4,
          label: '二级 1-1',
          children: [{
            id: 9,
            label: '三级 1-1-1'
          }, {
            id: 10,
            label: '三级 1-1-2'
          }]
        }]
      }, {
        id: 2,
        label: '一级 2',
        children: [{
          id: 5,
          label: '二级 2-1'
        }, {
          id: 6,
          label: '二级 2-2'
        }]
      }, {
        id: 3,
        label: '一级 3',
        children: [{
          id: 7,
          label: '二级 3-1'
        }, {
          id: 8,
          label: '二级 3-2'
        }]
      }],
      defaultProps: {
        children: 'children',
        label: 'label'
      }
    }
  },
  methods: {
    logout() {
      window.sessionStorage.clear()
      this.$router.push('/login')
    },
    getCheckedNodes() {
      console.log(this.$refs.tree.getCheckedNodes());
      console.log(this.$refs.tree.getCheckedNodes([1]));
    },
  }
}
</script>

<style lang="less" scoped>

</style>
