<template>
	<div class="condition">
		<span v-if="selected.value && index > 0" class="condition__label">И</span>
		<div class="condition__header">
			<span class="condition__title">Условие {{index + 1}}</span>
			<div class="condition__select">
				<v-select 
					v-model="selected" 
					:options="options"
					label="text"
					@input="onSelectChange"
				></v-select>
			</div>
		</div>
		
		<div class="condition__body">
			<RuleBuilder 
				:selected-condition="selected.value"
			></RuleBuilder>
		</div>

		<div class="condition__footer">
			<button @click="deleteCondiotion(index)">
				<i class="fas fa-trash-alt"></i>
				Удалить условие
			</button>
		</div>
	</div>
</template>

<script>
	import vSelect from 'vue-select'
	import 'vue-select/dist/vue-select.css';
	import RuleBuilder from '@/components/RuleBuilder';

	export default {
		name: 'Condition',

		components: {
			vSelect,
			RuleBuilder
		},

		props: {
			index: {
				type: Number,
				default: 0 
			}
		},

		data() {
			return {
				selected: {
					text: 'Выберите условие',
					value: null
				}, // TODO: set to placeholder
				options: [
					{
						text: 'Возраст респондента',
						value: 'clientAge'
					},
					{
						text: 'Тип карты лояльности',
						value: 'cardType'
					},
					{
						text: 'Статус лояльности',
						value: 'cardStatus'
					}
				]
			}
		},

		methods: {
			onSelectChange() {
				console.log('cahnge')
				this.$emit('input', {
					work: "its work"
				})
			},
			
			deleteCondiotion (index) {
				this.$emit('on-delete', index)
			}
		},
	}
</script>

<style lang="scss" scoped>

	.condition + .condition {
		border-top: 1px solid #ccc;
	}

	.condition {
		padding: 20px;
		background: #e4e4e4;

		&__label {
			position: relative;
			top: -30px;
			padding: 9px 15px;
			font-size: 16px;
			background: #47c758;
			border-radius: 10px;
		}

		&__header {
			display: flex;
			align-items: center;
			justify-content: space-between;
		}

		&__footer {
			padding: 15px 0;
			text-align: right;
		}

		&__title {
			flex: 1 1 30%;
			font-size: 18px;
			font-weight: 700;
		}

		&__select {
			flex: 1 1 70%;
			background: #fff;
    	border-radius: 4px;
		}
	}
</style>