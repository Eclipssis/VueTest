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
		name: 'cardStatusTemplate',

		components: {
			vSelect
		},

		data() {
			return {
				selected: null,
				options: [
					{
						text: 'Активна',
						value: 'active'
					},
					{
						text: 'Не активна',
						value: 'inactive'
					},
					{
						text: 'Заблокирована',
						value: 'blocked'
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