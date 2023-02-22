<script>
import BaseInput from '../components/BaseInput.vue';

//set initial value
const initialValue = {
  name: '',
  description: '',
  completed: false,
};

export default {
  name: 'ListView',
  //declare componen
  components: {
    BaseInput,
  },
  //declare data
  data: () => ({
    list: [
      {
        name: 'List Pertama',
      },
      {
        name: 'List Kedua',
      },
    ],
    //input data
    input: { ...initialValue },
  }),
  //declare methods
  methods: {
    //reset form
    resetForm() {
      Object.assign(this.input, initialValue);
    },
    //add list
    addList() {
      if (this.input.name == '') {
        alert('Please input name');
      } else {
        this.list.push({ ...this.input });
      }

      this.resetForm();
    },
    submitForm() {
      this.list = [...this.list, { ...this.input }];
      this.resetForm();
    },
  },
};
</script>
<template>
  <div>
    <h1>This is a list page</h1>
    <!-- <input
      type="text"
      v-model="input.name"
      placeholder="Input Name"
      @keyup.enter="() => addList()"
    /> -->

    <form @submit.prevent="() => submitForm()" method="post">
      <base-input v-model="input.name" placeholder="todo name"></base-input>
      <br />
      <base-input
        v-model="input.description"
        placeholder="todo deskripsi"
      ></base-input>

      <button type="submit">Add Todo</button>
    </form>

    <!-- <BaseInput></BaseInput> -->

    <ol>
      <template v-for="(item, index) in list" :key="index">
        <li>
          {{ item.name }}
        </li>
      </template>
    </ol>
  </div>
</template>
<style></style>
