<template lang="pug">
  el-container
    side-component
    el-container.is-vertical
      header-component
      router-view
</template>

<script>
import Side from './side'
import Header from './header'

export default {
  name: 'Container',
  components: {
    'side-component': Side,
    'header-component': Header,
  }
}
</script>
