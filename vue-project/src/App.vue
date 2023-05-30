<template>
  <div>
    <!-- <h1>{{ message }}</h1> -->
    <!-- <element-view></element-view> -->
    <!-- 员工管理 -->
    <!-- <emp-view></emp-view> -->
    <RouterView></RouterView>

  </div>
</template>
<script>
/* import EmpView from './views/tlias/EmpView.vue'; */

// import ElementView from './views/Element/ElementView.vue'
export default {
  components: { /* EmpView */ },
  data() {
    return {
      message: "Hello Vue!"
    }
  },
  methods: {

  }
}
</script>
<style></style>
