<template>
	<div>
		<tabs>
			<tab name="Логика">
					First tab content
			</tab>
			<tab name="Условия">
					Second tab content
			</tab>
			<tab name="Респонденты">
				<div class="tab-context-header">
					Добавить опрос
				</div>
				<div class="tab-context-body">
					<Condition 
						v-model="conditions[index]"
						v-for="(item, index) in conditions" 
						:key="index" 
						:index="index"
						@on-delete="deleteCondition"
					>
					</Condition>

					<div class="add-condition-block">
						<button @click="addCondition" class="add-condition-btn">
							<i class="fas fa-plus"></i>
						</button>
						<span class="add-condition-text">Нажмите, чтобы добавить новое условие выборки. <br>
						Все условия связываются между собой логическим "И"</span>
					</div>
				</div>
			</tab>
    </tabs>

	</div>
</template>

<script>
	import Vue from 'vue'
	import Condition from '~/components/Condition.vue'
	import Tabs from 'vue-tabs-component';


	Vue.use(Tabs);

	export default {
		components: {
			Condition
		},

		data() {
			return {
				conditions: []
			}
		},

		methods: { 	
			addCondition() {
				this.conditions.push({})
			},

			deleteCondition (index) {
				this.conditions.splice(index, 1)
			}
  	}
	}
</script>

<style lang="scss">
	.tabs-component {
		&-tabs {
			list-style-type: none;
			display: flex;
			border-bottom: 1px solid #80df13; // TODO: вынести цвет в переменную
		}

		&-tab {
			padding: 10px;
			margin-right: 15px;
			border-bottom: 2px solid transparent;
			&.is-active {
				font-weight: 700;
				color: #000;
				border-bottom: 2px solid #80df13; // TODO: вынести цвет в переменную
			}
		}

		&-tab.is-active &-tab-a {
			color: #000;
		}

		&-tab-a {
			color: green;
			font-size: 18px;
			text-decoration: none;
		}
	}

	.tab-context-header {
		padding: 20px;
		font-size: 16px;
		font-weight: 700;
		color: #bebebe;
	}

	.tabs-component-panels {
		min-height: 200px;
		box-shadow: 0px 4px 6px rgb(223, 223, 223);
		padding-bottom: 20px;
	}

	.add-condition-block {
		border: 1px solid #b3b3b3;
		border-radius: 4px;
		padding: 15px;
		text-align: center;
		margin: 20px;
	}

	.add-condition-btn {
		border: none; 
		background: none;
		color: #80df13;
		font-weight: 300;
		font-size: 35px;
		cursor: pointer;
		&:hover {
			color: darken($color: #80df13, $amount: 10%)
		}
	}

	.add-condition-text {
		display: block;
		color: #80df13;
	}
</style>