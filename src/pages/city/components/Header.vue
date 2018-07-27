<template>
	<div class="header">
		城市选择
		<router-link to='/'>
			<div class="iconfont header-back">&#xe624;</div>
		</router-link>
	</div>
</template>

<script>
export default {
	name: 'CityHeader'
}
</script>

<style scoped>
	.header{
		overflow: hidden;
		height: .86rem;
		line-height: .86rem;
		text-align: center;
		color: #fff;
		background: #00bcd4;
		font-size: .32rem;
		position: relative;
	}
	.header-back{
		width: .64rem;
		text-align: center;
		position: absolute;
		left: 0;
		top: 0;
		font-weight: 900;
		color: #fff;
	}
</style>