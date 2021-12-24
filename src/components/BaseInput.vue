<template>
	<label for=""> {{ label }}</label>
    <input 
    v-bind="$attrs"
   	:placeholder="label"
    class="border border-gray-400 p-4 rounded-lg"
    :value="modelValue" 
    @input="$emit('update:modelValue', $event.target.value)"
    />
</template>


<script>
export default {
    props: {
        label: {
           type: String,
           default: ''
        },
        modelValue:{
        	type: [String, Number],
        	default: ''
        }
    }
}
</script>