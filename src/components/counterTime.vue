<template>
  <div>
    <span>{{hour < 10 ?  '0' + hour : hour}}:{{minute < 10 ? '0' + minute : minute }}:{{second < 10 ? '0' + second : second}}</span>
  </div>
</template>

<script>
export default {
    name: 'counterTime',
    props:{
       hour: { 
      type: Number,
      default: 0},
    minute: { 
      type: Number,
      default: 0},
    second: { 
      type: Number,
      default: 0},
    },
    data(){
        return{
           
        }
    }
}
</script>

<style scoped>
div, span{
  margin-bottom: 20px;
  font-size: 40px;
}
</style>