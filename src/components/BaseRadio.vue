<template>
	<input 
	v-bind="$attrs"
	type="radio" 
	:checked="movelValue===value"
	:value="value"
	
	>
	<label v-if="label">{{label}}</label>

</template>

<script>
	export default{
		props:{
			label:{
				type: String,
				default: ''
			},
			modelValue:{
				type: [String, Number],
				default: ''
			},
			value:{
				type: [String, Number],
				required: true
			}
		}
	}
</script>