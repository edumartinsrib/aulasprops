<template>
  <button>{{ textValue }}</button>
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
.btnS {
  
  margin-bottom: 15px;
  
}
</style>