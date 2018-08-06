<template>
	<div>
		<div class="search">
			<input class="search-input" type="text" placeholder="输入城市名或拼音">
		</div>
		<div class="search-content">
			<ul>
				<li>123</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {
	name: 'CitySearch'
}
</script>

<style scoped>
	.search{
		height: .72rem;
		padding: 0 .1rem;
		background: #00bcd4;
	}
	.search-input{
		width: 100%;
		height: .62rem;
		line-height: .62rem;
		text-align: center;
		border-radius: .06rem;
	}
	.search-content{
		
	}
	
</style>