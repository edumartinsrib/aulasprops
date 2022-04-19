<template>
  <button class="buttons">{{ textValue }}</button>
</template>

<script>
export default {
  name: "buttonsTimer",
  props: {
    event: String,
    textValue: String,
    classValue: String,
  },
  data() {
    return {};
  },
};
</script>

<style>
.buttons{
    display: inline-block;
margin-bottom: 5px;
}
</style>