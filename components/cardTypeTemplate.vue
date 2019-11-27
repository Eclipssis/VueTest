<template>
	<div>
		<v-select 
			v-model="selected" 
			:options="options"
			label="text"
			@input="onSelectChange"
		></v-select>
	</div>
</template>

<script>
	import vSelect from 'vue-select'

	export default {
		name: 'cardTypeTemplate',

		components: {
			vSelect
		},

		data() {
			return {
				selected: null,
				options: [
					{
						text: 'Gold',
						value: 'gold'
					},
					{
						text: 'Silver',
						value: 'silver'
					},
					{
						text: 'Platimun',
						value: 'platimun'
					}
				]
			}
		},

		methods: {
			onSelectChange() {
				
			}
		},
	}
</script>

<style lang="scss" scoped>

</style>