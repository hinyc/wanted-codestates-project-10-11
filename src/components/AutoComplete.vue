<template>
  <div class="dropdown-container">
    <ul>
      <li class="dropdown-item" @click="onClickHandler">
        {{ companies[0] }}
      </li>
      <li class="dropdown-item" @click="onClickHandler">{{ companies[1] }}</li>
      <li class="dropdown-item" @click="onClickHandler">{{ companies[2] }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: ['companies', 'setInputValue'],
  methods: {
    onClickHandler(e) {
      this.$emit('setInputValue', e.target.textContent);
    },
  },
};
</script>

<style>
.dropdown-container {
  position: absolute;
  top: 176px;
  z-index: 9;
  width: 328px;
  height: auto;
  padding: 10px;
  border: 1px solid #f2f2f2;
  border-radius: 8px;
  background: #fff;
}
.dropdown-item {
  padding: 10px;
  font-size: 14px;
  cursor: pointer;
}
.dropdown-item:hover {
  background: #f8f8f8;
}
</style>
