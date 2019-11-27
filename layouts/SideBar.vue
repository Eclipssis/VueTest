<template>
	<aside class="side-bar">
		<a class="logo" href="/">
			<span class="logo-icon"></span>
		</a>

		<nav>
			<ul class="menu">
				<router-link to="/quiz" tag="li" class="menu__item">
					<span class="menu__icon"><i class="fas fa-file-alt"></i></span>
					<span class="menu__text">Опросы</span>
				</router-link>

				<router-link to="/users" tag="li" class="menu__item">
					<span class="menu__icon"><i class="fas fa-users"></i></span>
					<span class="menu__text">Пользователи</span>
				</router-link>

				<router-link to="/blackList" tag="li" class="menu__item">
					<span class="menu__icon"><i class="fas fa-skull-crossbones"></i></span>
					<span class="menu__text">Черные списки</span>
				</router-link>

				<router-link to="/callCenter" tag="li" class="menu__item">
					<span class="menu__icon"><i class="fas fa-phone"></i></span>
					<span class="menu__text">Колл центр</span>
				</router-link>
			</ul>
		</nav>
	</aside>
</template>

<script>
	export default {
		name: 'SideBar'
	}
</script>

<style lang="scss" scoped>
	.logo {
		border-radius: 50%;
		display: inline-block;
		margin-bottom: 20px;
	}

	.logo-icon {
		display: inline-block;
		width: 60px;
		height: 60px;
		border-radius: 50%;
		overflow: hidden;
		background: rgb(189, 10, 10);
	}

	.side-bar {
		text-align: center;
		padding: 15px 20px;
		background: rgba(235, 235, 235, 0.36078);
		box-shadow: 2px 0px 10px rgb(230, 230, 230);
	}

	.menu {
		list-style-type: none;
		&__item {
			display: flex;
			flex-direction: column;
			text-align: center;
			padding: 15px 10px;
			border-radius: 6px;
			margin-bottom: 10px;
			color: #555;
			cursor: pointer;
			border: 1px solid transparent;
			transition: all 0.15s ease;
			
			&:hover {
				color: #80df13; // TODO: вынести цвет в переменную
				border: 1px solid #80df13; // TODO: вынести цвет в переменную
			}

			&.nuxt-link-active {
				background: #efefef;
				border: 1px solid #efefef;
				&:hover {
					color: #555;
				}
			}
		}
		&__text {
    	display: inline-block;
			min-width: 120px;
			font-size: 16px;
			font-weight: 600;
		}
		&__icon {
			font-size: 22px;
		}
	}
</style>