<template>
  <div class="tasks">
    <ul class="tasks__list">
      <li class="tasks__list-item" v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <span @click="$emit('removeTask', index)"> &#x2716; </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    tasks: Array,
  },
};
</script>

<style lang="scss">
.tasks {
  &__list {
    margin-top: 100px;
  }

  &__list-item {
    position: relative;
    display: block;
    background-color: #fff;
    border-radius: 20px;
    padding: 15px 12px;
    font-size: 24px;
    color: rgb(21, 52, 123);
    word-break: break-all;

    &:not(:last-child) {
      margin-bottom: 10px;
    }

    & span {
      position: absolute;
      top: 2px;
      right: 8px;
      font-size: 13px;
      color: rgb(229, 99, 99);
      cursor: pointer;
      padding: 3px;
    }
  }
}
</style>
