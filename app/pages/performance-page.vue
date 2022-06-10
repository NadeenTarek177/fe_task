<template>
  <div class="c-dashboard">
    <div class="c-filters__container">
      <label for="Start" >Start date:</label>
      <input type="date" id="Start" name="Start_data" v-model='startData' >
      <label for="End">End date:</label>
      <input type="date" id="End" name="End_data"  v-model='endData' >

    </div>
    <div class="c-dashboard__header">
      <performance-chart-component :start="startData" :end="endData" />
    </div>
  </div>
</template>

<script>
import PerformanceChartComponent from "../components/vue-components/performance-chart.vue";
export default {
  name: "AboutPageComponent",
  components: {
    PerformanceChartComponent,
  },
  data() {
      return {
        startData:"",
        endData:"",
      };
  },
  methods: {
    view() {

  },
  handleChange () {

    console.log(event.target);
      const { name, value } = event.target;
      //this.startData=value;
      console.log(name,"**",value);
      console.log(this.startData ,"--",this.endData);
    },
  handleChangeEnd () {
        console.log("k",this.startData)
        console.log(event.target);
      const { name, value } = event.target;
       this.endData=value;
      console.log(name,value ,this.endData);


  }
}
}
</script>
