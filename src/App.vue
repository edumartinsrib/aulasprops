<template>
  <div class="main">
    <h1 class="mt-3">Cronômetro - DEVInHouse</h1>
    <hr />
    <counterTime
      :hour="hourValue"
      :minute="minuteValue"
      :second="secondValue"
    />
    <buttonsTimer
      :textValue="textValor"
      :class="classValor"
      @click="startCount()"
    />
    <buttonsTimer
      :textValue="textValor3"
      :class="classValor3"
      @click="LimparCampo()"
    />
    <tableData :dados="arrData" v-show="secondValue" />
    <buttonsTimer
      :textValue="textValor2"
      :class="classValor2"
      @click="saveData()"
      v-show="secondValue"
    />
  </div>
</template>

<script>
import buttonsTimer from "./components/buttonsTimer.vue";
import tableData from "./components/tableData.vue";
import counterTime from "./components/counterTime.vue";

export default {
  name: "App",

  components: {
    buttonsTimer,
    tableData,
    counterTime,
  },
  data() {
    return {
      timer: null,
      textValor: null,
      textValor2: null,
      textValor3: null,
      classValor: null,
      classValor2: null,
      classValor3: null,
      hourValue: 0,
      minuteValue: 0,
      secondValue: 0,
      interval: null,
      arrData: [],
      idCont: 0,
    };
  },
  methods: {
    startCount() {
      this.timer += 1;
      this.changeStatus();
    },

    changeStatus() {
      if (this.textValor === "Iniciar") {
        this.counterTime();
        this.textValor = "Encerrar";
        this.classValor = "btnS btn btn-danger";
      } else {
        this.StopCounter();
        this.textValor = "Iniciar";
        this.classValor = "btnS btn btn-success";
      }
    },
    counterTime() {
      this.interval = setInterval(() => {
        this.secondValue += 1;
        this.secondValue === 60
          ? (this.minuteValue++, (this.secondValue = 0))
          : "";
        this.minuteValue === 60 ? this.hourValue++ : "";
      }, 1000);
    },

    StopCounter() {
      clearInterval(this.interval);
    },
    saveData() {
      this.arrData.push({
        id: this.idCont++,
        valor: `0${this.hourValue}:0${this.minuteValue}:${this.secondValue}`,
      });
      console.log(this.arrData);
    },
    LimparCampo() {
      this.secondValue = 0;
      this.secondValue = 0;
      this.minuteValue = 0;
      this.changeStatus();
      this.arrData = [];
    },
  },
  created() {
    this.textValor = "Iniciar";
    this.classValor = "btnS btn btn-success";
    this.textValor2 = "Registrar";
    this.classValor2 = "btn btn-dark mt-2 ";
    this.textValor3 = "Limpar";
    this.classValor3 = "btn btn-dark ";
  },
};
</script>

<style>
h1,
h2 {
  text-align: center;
}
div.main {
  text-align: center;
}
.btn-dark {
  color: aliceblue;
  margin-left: 10px;
}
</style>
