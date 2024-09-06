<template>
  <div>
    <table class="table container" border="2">
      <thead>
        <tr>
          <th scope="col">S.N</th>
          <th scope="col">Name</th>
          <th scope="col">Address</th>
          <th scope="col">Email</th>
          <th scope="col">Password</th>
          <th scope="col">Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(element, index) in informations" :key="index">
          <th>{{ index + 1 }}</th>
          <td>{{ element.name }}</td>
          <td>{{ element.address }}</td>
          <td>{{ element.email }}</td>
          <td>{{ element.password }}</td>
          <td>
            <button
              class="btn btn-warning btn-sm"
              @click="$emit('edit', index)"
            >
              Edit
            </button>
            <button
              style="margin-left: 10px"
              class="btn btn-danger btn-sm"
              @click="$emit('delete', index)"
            >
              Delete
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "MyTable",

  components: {},
  data() {
    return {
      //   Informations: [
      //     {
      //       name: "Shiva",
      //       address: "Dang",
      //       email: "shiva499@gmail.com",
      //       password: "123456",
      //     },
      //     {
      //       name: "Bipin",
      //       address: "Dang",
      //       email: "shiva499@gmail.com",
      //       password: "123456",
      //     },
      //     {
      //       name: "Naran",
      //       address: "Dang",
      //       email: "shiva499@gmail.com",
      //       password: "123456",
      //     },
      //   ],
    };
  },
  props: {
    informations: Array,
  },
  methods: {},
};
</script>

<style></style>
