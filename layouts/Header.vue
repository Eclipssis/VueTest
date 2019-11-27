<template>
	<header class="header">
		<div class="header__section">

			<!-- TODO: можно вынести в компонент -->
			<form class="search">
				<input class="search__text" type="text" placeholder="Поиск по системе">
				<span class="search__icon"><i class="fa fa-search"></i></span>
			</form>

		</div>
		<div class="header__section">
			<div class="user-panel">
				<div class="user-info">
					<img src="https://lh3.googleusercontent.com/-R7B9RNe_0SU/AAAAAAAAAAI/AAAAAAAAAAA/ACHi3rco2PlNIIBSPMBiZH_kYWxhs8g3Xg/photo.jpg?sz=46" class="user-info__image">
					<div class="user-info__inner">
						<span class="user-info__main-text">Puchkovskiy A.</span>	
						<span class="user-info__secondary-text">Администратор</span>	
					</div> 
				</div>
			</div>
		</div>
	</header>
</template>

<script>
	export default {
		name: 'Header'
	}
</script>

<style lang="scss" scoped>
	.header {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 20px;
		padding: 20px 40px;
		background: rgba(235, 235, 235, 0.36078);
		box-shadow: 7px 0px 7px #d0d0d0;

		&__section {
			padding: 10px 0;
			flex: 1 1;
		}
	}

	.search {
		position: relative;
		width: 40vw;
		&__text {
			width: 100%;
			border: 1px solid rgb(134, 134, 134);
			color: rgb(134, 134, 134);
			padding: 12px;
			height: 30px;
			border-radius: 4px;
		}
		&__icon {
			position: absolute;
			top: 50%;
			right: 10px;
			transform: translate(0, -50%);
		}
	}

	.user-info {
		display: flex;
		justify-content: flex-end;
		align-items: center;
		
		&__image {
			margin-right: 10px;
			overflow: hidden;
			border-radius: 50%;
		}

		&__inner {
			display: flex;
			flex-direction: column;
		}

		&__main-text {
			font-size: 16px;
			font-weight: 700;
		}
	}
</style>