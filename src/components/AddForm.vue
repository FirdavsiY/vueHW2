<template>
  <div id="addForm">
    <!-- <form @submit="ChildFunction"> -->
      <input type="text" placeholder="Provide something" v-model="inputValue" />
      <button @click="ChildFunction">Add</button>
    <!-- </form> -->
  </div>
</template>

<script>
export default {
  name: "AddForm",
  data() {
    return {    
      inputValue: "",
    };
  },
  methods: {
    ChildFunction: function () {
      this.$emit("ShareMyScreams", this.inputValue);
      this.inputValue = "";
    },
  },
};
</script>

<style>
#addForm {
  display: flex;
  justify-content: center;
  width: 100%;
  height: fit-content;
}
#addForm input {
  outline: none;
  width: 321px;
  height: 42px;

  border: 2px solid #007fff;
  box-sizing: border-box;
  border-radius: 10px;
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 20px;
  padding-left: 20px;

  color: #000000;
}
#addForm button {
  margin-left: 8px;

  width: 155px;
  height: 42px;
  border: none;
  outline: none;
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 22px;
  /* identical to box height */

  text-align: center;

  color: #ffffff;

  background: #0071e3;
  border-radius: 10px;
}
</style>
