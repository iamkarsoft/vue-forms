<template>
	<label v-if="label">{{ label }}</label>
        <select name=""
          v-bind="{...$attrs,
          	onChange: ($event) =>{ $emit('update:modelValue', $event.target.value)}
      		}"
          :value="modelValue"
          class="border border-gray-400 p-4 rounded-lg"

          >
          <option v-for="option in options"
          :value="option"
          :key="option"
          :selected="option === modelValue"
          >{{option}}</option>
       
        </select>
</template>


<script>
export default{

	props: {
		label:{
			type: String,
			default: ''
		},
		modelValue: {
			type: [String, Number],
			default: ''
		},
		options:{
			type: Array,
			required: true
		}
	}
}
	
</script>