<template>
  <div>
    <form class="container form-container" @submit.prevent="submitHandler">
      <div class="mb-3">
        <label for="name" class="form-label">Name:</label>
        <input
          v-model="formData.name"
          type="name"
          class="form-control"
          id="name"
        />
      </div>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Email</label>
        <input
          v-model="formData.email"
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
      </div>
      <div class="mb-3">
        <label for="address" class="form-label">Address</label>
        <input
          v-model="formData.address"
          type="text"
          class="form-control"
          id="address"
        />
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <input
          v-model="formData.password"
          type="password"
          class="form-control"
          id="exampleInputPassword1"
        />
      </div>

      <button type="submit" class="btn btn-primary">
        {{ isEdit ? "Update" : "submit" }}
      </button>
    </form>
    <h2 class="container">My form data</h2>
    <MyTable
      :informations="submittedData"
      @edit="editHandler"
      @delete="deleteHandler"
    />
  </div>
</template>

<script>
import MyTable from "./MyTable.vue";
export default {
  name: "MyForm",

  components: {
    MyTable,
  },
  data() {
    return {
      formData: {
        name: "",
        address: "",
        email: "",
        password: "",
      },
      submittedData: JSON.parse(localStorage.getItem("Informations")) || [],
      isEdit: false,
      editIndex: null,
    };
  },
  props: {},
  methods: {
    submitHandler() {
      if (this.isEdit) {
        this.submittedData.splice(this.editIndex, 1, { ...this.formData });
        this.isEdit = false;
        this.editIndex = null;
      } else {
        this.submittedData.push(...this.formData);
      }

      this.saveTolocalStorage();
      this.formData = {};
    },
    saveTolocalStorage() {
      localStorage.setItem("informations", JSON.stringify(this.submittedData));
    },
    editHandler(index) {
      this.formData = { ...this.submittedData[index] };
      this.isEdit = true;
      this.editIndex = index;
    },
    deleteHandler(index) {
      this.submittedData.splice(index, 1);
      this.saveTolocalStorage();
    },
  },
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
