<template>
    <div 
        class="checkbox"
        @click="$emit('update:modelValue', !modelValue)"
        :class="modelValue ? 'checked' : 'unchecked'"
    >
        <img 
            v-if="modelValue"
            class="checkbox-icon"
            src="../assets/icons/checked.svg"
            alt="checked"
        />
        <img
            v-else
            class="checkbox-icon"
            src="../assets/icons/cross.svg"
            alt="unchecked"
        />
    </div>
</template>

<style lang="scss" scoped>
.checkbox {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 18px;
    height: 18px;
    border-radius: 5px;
    background-color: #EC5F6B;
    &.checked {
        background-color: #5E6DEC;
    }
}

</style>

<script>
export default {
	props: {
		modelValue: {
			type: Number,
			required: true,
		},
		max: {
			type: Number,
			required: false,
			default: 100,
		},
		min: {
			type: Number,
			required: false,
			default: 0,
		},
	},
	emits: ['update:modelValue'],
}
</script>
