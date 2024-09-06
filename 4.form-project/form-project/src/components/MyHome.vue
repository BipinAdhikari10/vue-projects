<template>
  <div>
    <MyNavigation />
    <MyForm />

    <MyTable />
    <MyFooter />
  </div>
</template>

<script>
import MyNavigation from "./MyNavigation.vue";
import MyForm from "./MyForm.vue";
import MyTable from "./MyTable.vue";
import MyFooter from "./MyFooter.vue";
export default {
  name: "MyHome",

  components: {
    MyNavigation,
    MyForm,

    MyTable,
    MyFooter,
  },

  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<style></style>
