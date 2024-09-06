<template>
  <div>
    <form class="container form-container">
      <div class="mb-3">
        <label for="name" class="form-label">Name:</label>
        <input type="name" class="form-control" id="name" />
      </div>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Email</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
      </div>
      <div class="mb-3">
        <label for="address" class="form-label">Address</label>
        <input type="text" class="form-control" id="address" />
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <input
          type="password"
          class="form-control"
          id="exampleInputPassword1"
        />
      </div>

      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "MyForm",

  components: {},
  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<style scoped>
.form-container {
  width: 60%;
  padding: 10px;
  margin-top: 50px;
  box-shadow: 0px 4px 8px 0px rgba(0, 0, 0, 0.2);
}
</style>
