<script setup>
	import {ref} from 'vue';
	const props = defineProps({
		count:{
			type:Number,
			default:0
		}
	});
	const count = ref(props.count);
	function incree() {
		return count.value++;
	}
	function decree() {
		return count.value--;
	}
	
</script>
<template>
	<div class="row">
		<div class="col-1">
			<button @click="incree" class="btn btn-outline-primary form-control">+</button>
		</div>
		<div class="col-1">
			<span>{{ count }}</span>
		</div>
		<div class="col-1">
			<button @click="decree" class="btn btn-outline-danger form-control">-</button>
		</div>
	</div>	
</template>
<style scoped>
	button{
		font-weight:bolder;
	}
	span {
	    position: relative;
	    justify-content: center;
	    align-items: center;
	    display: flex;
	    height: 100%;
	}
</style>