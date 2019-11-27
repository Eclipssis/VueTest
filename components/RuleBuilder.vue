<template>
	<div class="rule-list" v-if="selectedCondition">
		<div class="rule" v-for="(rule, index) in rules" :key="index">
			<div class="rule__header">
				{{ruleOptions[selectedCondition].label}} {{index +1}}
			</div>

			<div class="rule__body">
				<div class="rule__inner-component">
					<component :is="ruleOptions[selectedCondition].template"></component>
				</div>
				<span @click="removeRule">
					<i class="fas fa-trash-alt"></i>
				</span>
			</div>
		</div>

		<button @click="addRule" class="add-rule-btn">
			<i class="fas fa-trash-alt"></i>
			Добавить {{ruleOptions[selectedCondition].label}}
		</button>
	</div>
</template>

<script>
	import cardStatusTemplate from "@/components/cardStatusTemplate";
	import clientAgeTemplage from "@/components/clientAgeTemplage";
	import cardTypeTemplate from "@/components/cardTypeTemplate";

	export default {
		name: 'RuleBuilder',

		components: {
			cardStatusTemplate
		},

		props: {
			selectedCondition: {
				type: [String, null],
				default: ''
			},
		},

		data() {
			return {
				rules: [],
				ruleOptions: {
					clientAge: {
						label: "Диапазон",
						template: clientAgeTemplage
					},
					cardType: {
						label: "Тип",
						template: cardTypeTemplate
					},
					cardStatus: {
						label: 'Статус',
						template: cardStatusTemplate
					}
				}
			}
		},

		computed: {
			name() {
				return this.data 
			}
		},

		methods: {
			addRule() {
				this.rules.push({})
			},

			removeRule (index) {
				this.rules.splice(index, 1)
			}
		},
	}
</script>

<style lang="scss" scoped>
	
	.rule-list {
		padding: 15px 0;
	}
	
	.rule {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 15px;
		&__header {
			flex: 1 1 30%;
		}

		&__inner-component {
			flex: 1 1;
		}

		&__body {
			display: flex;
			flex: 1 1 70%;
		}
	}

	.add-rule-btn {
		position: relative;
    bottom: -35px;
		margin-left: 30%;
	}
</style>