<template lang="pug">
  el-main
    el-row(type="flex",justify="center")
      el-card.box-card
        .clearfix(slot="header")
          span Login
          el-button(style="float: right; padding: 3px 0", type="text") Operation button
        .text.item
          el-form(ref="form", :model="form", label-width="120px")
            el-form-item(label="Login ID")
              el-input(v-model="form.id")
            el-form-item(label="password")
              el-input(v-model="form.password")
            el-form-item
              el-button(type="primary" @click="login") Login
</template>

<script>
  export default {
    data() {
      return {
        form: {
          id: '',
          password: ''
        }
      }
    },
    methods: {
      login() {
        this.$store.state.count = true;
        this.$router.push('/dashboard');
      }
    }
  }
  
  const getters = {
    isAuthenticated: state => !!state.token,
    authStatus: state => state.status,
  }

</script>
