<style lang="scss">
  .layout-items {
    display: flex;
    &-left {
      flex-grow: 1;
      overflow: scroll;
    }
    &-right {
      border-left: 1px solid #bbb;
    }
  }
</style>

<template>
  <div class="layout-items">
    <list-view class="layout-items-left" :memos="memos"></list-view>
    <router-view class="layout-items-right"></router-view>
  </div>
</template>

<script>
  import ListView from '../components/ListView'
  export default{
    props: {
      memos: Array
    },
    methods: {
      remove(id) {
        this.$emit('remove', id)
      }
    },
    components: {
      ListView
    }
  }
</script>
