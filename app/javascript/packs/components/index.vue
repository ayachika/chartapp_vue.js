<template>
  <div class=container>
    <h3>timemanegementapp</h3>
    <ScatterChart/>
    <!--入力フォームを追加-->
    <form>
      <label>
        task<input type="text" name="" v-model="nameSet" placeholder="洗濯">
      </label><br></br>
      <label>
        important<input type="number" name="" v-model.number="numImportant"> 
      </label><br></br>
      <label>
        urgent<input type="number" name="" v-model.number="numUrgent">
      </label><br></rb>
      <!--clickしたらイベントが発火するように設定-->
      <input type="button" value="add" @click="addChartList()">      
    </form>
    
    
  </div>
</template>

<script>
// インポート
import { Scatter } from 'vue-chartjs'

var ScatterChart = {
  extends: Scatter,
  mounted () {
    this.renderChart({
      datasets: [{
      //ラベル
      label:'todotasks',
      fill: false,
      borderColor: '#f87979',
      backgroundColor: '#f87979',
      //データ詳細
      data:[{
        numImportant:'',
        numUrgent:'',
        //ここに新しいデータが入る？
        }],
    }]
},{
  
addChartList: function(){
  
  //configの中にinputを入力して値をpush
chart.data.labels.push(this.nameSet);
chart.data.datasets.push(this.numImportant);
chart.data.datasets.push(this.numUrgent);
  
chart.update();
  
  this.nameSet = "洗濯";
  this.numImportant = "10";
  this.numUrgent = "10";
},responsive: true,maintainAspectRatio: false})
}
}


export default {
  name: 'Test',
  components: {
    ScatterChart
  }
} 

</script>

<style scoped>

.container{
  width:40%;
  height:40%;
}



</style>