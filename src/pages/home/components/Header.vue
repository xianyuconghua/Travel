<template>
	<div class="header">
		<div class="header-left">
			<span class="iconfont back-icon">&#xe624;</span>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<router-link to='/city'>
			<div class="header-right">
				{{this.$store.state.city}}
				<span class="iconfont arrow-icon">&#xe64a;</span>
			</div>
		</router-link>
	</div>
</template>

<script>
export default {
	name: 'HomeHeader'
}
</script>

<style scoped>
/*1rem = 50px;*/
	.header{
		display: flex;
		line-height: .86rem;
		background: #00bcd4;
		color: #fff;
	}
	.header-left{
		width: .64rem;
		float: left;
		text-align:center;
	}
	.back-icon{
		font-weight: 900;
	}
	.header-input{
		flex: 1;
		height: .64rem;
		line-height: .62rem;
		margin: .12rem 0 0 .2rem;
		background: #fff;
		border-radius: .1rem;
		color: #ccc;
		padding-left: .2rem;
	}
	.header-right{
		/*width: 1.44rem;*/
		padding:0 .2rem;
		float: right;
		text-align: center;
		color: #fff;
	}
	.arrow-icon{
		font-size: .24rem;
	}
</style>