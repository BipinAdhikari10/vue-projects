<template>
  <div>
    <MyNavigation />
    <MyForm />
    <MyFooter />
    <MyTable />
  </div>
</template>

<script>
import MyNavigation from "./MyNavigation.vue";
import MyForm from "./MyForm.vue";

import MyFooter from "./MyFooter.vue";
// import MyTable from "./MyTable.vue";
export default {
  name: "MyHome",

  components: {
    MyNavigation,
    MyForm,
    MyFooter,
    // MyTable,
  },

  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<style></style>
