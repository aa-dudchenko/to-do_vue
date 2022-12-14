<template>
  <div class="input-block">
    <input
      class="input-block__input"
      v-model="inputValue"
      type="text"
      placeholder="your task"
      v-on:keyup.enter="handleAddTask"
    />
  </div>
</template>


<script>
export default {
  name: "InputBlock",

  data() {
    return {
      inputValue: "",
    };
  },

  methods: {
    handleAddTask: function () {
      if (this.inputValue !== "") {
        this.$emit("addTask", this.inputValue);
      }
      this.inputValue = "";
    },
  },
};
</script>


<style lang="scss">
.input-block {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;

  &__input {
    width: 50%;
    min-width: 280px;
    height: 50px;
    border: none;
    border-radius: 20px;
    padding: 0 15px;
    outline: none;
    &::placeholder {
      color: rgb(21, 52, 123);
    }
  }

  &__btn {
    width: 30%;
    min-width: 200px;
    height: 30px;
    border-radius: 25px;
    border: 1px solid #fff;
    background-color: rgb(21, 52, 123);
    color: #fff;
    cursor: pointer;
  }
}
</style>