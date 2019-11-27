<template>
	<div>
		<ul class="breadcrumb">
			<li class="breadcrumb__item">
				<a class="breadcrumb__link"><i class="fas fa-home"></i></a>
			</li>

			<li class="breadcrumb__item" v-for="(link, index) in pathArray" :key="index">
				<a class="breadcrumb__link">{{ linkMap[link] }}</a>
			</li>

		</ul>
	</div>
</template>

<script>
	export default {
		name: 'Breadcramb',

		data() {
			return {
				// TODO: can use multi language
				linkMap: {
					quiz: 'Опросы',
					users: 'Пользователи',
					blackList: 'Черный список',
					callCenter: 'Колл центер',
				}
			}
		},

		computed: {
			pathArray () {
				return this.$route.path.split('/').filter(item => item.length > 0)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.breadcrumb {
		list-style-type: none;
		display: flex;
		margin: 0 40px 20px;

		&__item {
			
		}

		&__item + &__item {
			&:before {
				margin: 0 7px;
				content: '->'
			}
		}
		&__link {}
	}
</style>