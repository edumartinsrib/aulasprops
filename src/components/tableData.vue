<template>
  <div>
     <table class="table table-dark">
  <thead>
      <tr>
     <th scope="col">ID</th>
      <th scope="col">Contagem</th>
      </tr>
  </thead>
  <tbody>
    <tr class="table-active" v-for="conts in dados" :key="conts.id">
      <th class="centralizar">
          <td>{{conts.id}}</td>
      </th>
      <th>
           <td>{{conts.valor}}</td>
      </th>
    </tr>
  </tbody>
</table>
  </div>
</template>

<script>
export default {
    name: 'tableData',
    props:{
        dados: Array,
    },
}
</script>

<style scoped>
.table{
    width: 300px;
    margin-top: 20px;
    margin: 0 auto;
}
.centralizar{
    text-align: center;
}
th{
    text-align: center;
}
</style>