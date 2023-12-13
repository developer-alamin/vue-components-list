<script setup>
	import {ref,onMounted} from "vue";
	const add = ref();
	const labels = ['Red','Blue','Yellow']
	const dataset = [300, 50, 100];
	const color = [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)'
    ];
	const data = {
		  labels:labels,
		  datasets: [{
		    label: 'My First Dataset',
		    data: dataset,
		    backgroundColor:color,
		    hoverOffset: 4
		  }]
		};
	const config = {
	  type: 'doughnut',
	  data: data,
	};
	onMounted(()=>{
		let ctx = document.getElementById("chart");
		Chart = new Chart(ctx,config);
	});
	function addPie () {
		dataset.push(Number(add.value));
		data.datasets[0].data = dataset;
		Chart.update();	
	}
</script>
<template>
	<div class="row">
		<div class="col-4">
  			<canvas id="chart"></canvas>
		</div>	
		<div class="col-3">
			<input v-model="add" type="number" class="form-control" placeholder="Number..."><br>
			<button @click="addPie()" class="btn form-control btn-outline-success">Add</button>
		</div>	
	</div>	
</template>
<style scoped>
.col-6{
	width:500px;
	height:500px;
}
</style>