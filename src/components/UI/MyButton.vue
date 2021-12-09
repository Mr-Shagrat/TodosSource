<template>
  <button class="btn"><slot></slot></button>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.btn {
  cursor: pointer;
  padding: 5px 10px;
  background: #ff8469;
  border-radius: 7px;
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  text-transform: uppercase;
  border: none;
  transition: all 0.2s ease-in;
  &:hover {
    background-color: #fd441b;
    transition: all 0.3s ease-in;
  }
  &:active {
    color: #4f5565;
    transition: all 0.1s ease-out;
  }
}
</style>