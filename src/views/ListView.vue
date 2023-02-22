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
    //add list
    addList() {
      if (this.input.name == '') {
        alert('Please input name');
      } else {
        this.list.push({ ...this.input });
      }

      //   this.list.push({ ...this.input });

      //assign object based on another object
      Object.assign(this.input, initialValue);
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

    <!-- <BaseInput></BaseInput> -->
    <base-input v-model="input.name" placeholder="todo name"></base-input>
    <br />
    <base-input
      v-model="input.description"
      placeholder="todo deskripsi"
    ></base-input>

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
