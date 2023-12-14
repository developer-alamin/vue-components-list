<script setup>
import {ref,computed} from "vue";
const props = defineProps(['person']);
const activePer = ref(0);
const persons = computed(() =>props.person[activePer.value]);
</script>
<template>
	<div class="col-3">
		<div class="list-group">
		  <button @click="activePer=index" v-for="(value,index) in person" :key="index" class="list-group-item list-group-item-action">{{ value.name}}</button>
		</div>
	</div>
	<div class="col-9">
		<div class="information">
			<div class="row">
				<div class="col-6">
					<h4>Aplication Information</h4>
					<p>Personal Details And Applicaion</p>
				</div>
				<div class="col-6">
					<img :src="persons.image" alt="">
				</div>
			</div>
			<hr>
			<div class="row">
				<div class="col-4">
					<b>Full Name:</b>
				</div>
				<div class="col-8">
					<p>{{ persons.name }}</p>
				</div>
			</div>
			<hr>
			<div class="row">
				<div class="col-4">
					<b>Application For:</b>
				</div>
				<div class="col-8">
					<p>{{ persons.position }}</p>
				</div>
			</div>
			<hr>
			<div class="row">
				<div class="col-4">
					<b>Email Address:</b>
				</div>
				<div class="col-8">
					<p>{{ persons.email }}</p>
				</div>
			</div>
			<hr>
			<div class="row">
				<div class="col-4">
					<b>Sallery:</b>
				</div>
				<div class="col-8">
					<p>{{ persons.sallery }}</p>
				</div>
			</div>
			<hr>
			<div class="row">
				<div class="col-4">
					<b>About:</b>
				</div>
				<div class="col-8">
					<p>{{ persons.about }}</p>
				</div>
			</div>
			<hr>
			<div class="row">
				<div class="col-4">
					<b>Attachments:</b>
				</div>
				<div class="col-8">
					<ul class="list-group">
					  <li v-for="(v,i) in persons.attachments" class="list-group-item d-flex justify-content-between align-items-center">
					    {{ v.name }} <span>{{ v.size }}</span>
					    <a href="">Download</a>
					  </li>
					</ul>
				</div>
			</div>
			<hr>
				
		</div>	
	</div>
</template>
<style scoped>
  img {
    width: 100px;
    height: 100px;
}
</style>