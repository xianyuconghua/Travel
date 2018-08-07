<template>
<div>
	<div class="banner" @click="handleBannerClick">
		<img class="banner-img" src="//img1.qunarzz.com/sight/p0/1611/56/561a69bf759fbdc8a3.water.jpg_600x330_a4968d4a.jpg" alt="">
		<div class="banner-info">
			<div class="banner-title">
				大连圣亚海洋世界(AAAA景区)
			</div>
			<div class="banner-number">
				<span class="iconfont banner-icon">&#xe692;</span>
				39
			</div>
		</div>
	</div>
	<common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
</div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
	name: 'DetailBanner',
	data() {		
		return {
			showGallary: false,
			imgs: ['//img1.qunarzz.com/sight/p0/1611/56/561a69bf759fbdc8a3.water.jpg_600x330_a4968d4a.jpg', '//img1.qunarzz.com/sight/p0/1503/33/33f6ddd58bf9811.water.jpg_600x330_f8f94057.jpg']
		}
	},
	methods: {
		handleBannerClick() {
			this.showGallary = true
		},
		handleGallaryClose() {
			this.showGallary = false
		}
	},
	components: {
		CommonGallary
	}
}
</script>

<style scoped>
	.banner{
		overflow: hidden;
		height: 0;
		padding-bottom: 55%;
		position:relative;
	}
	.banner-img{
		width: 100%;
	}
	.banner-info{
		display: flex;
		position: absolute;
		left: 0;
		right: 0;
		bottom: 0;
		line-height: .6rem;
		color: #fff;
		background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
	}
	.banner-title{
		flex: 1;
		font-size: .32rem;
		padding:0 .2rem;
	}
	.banner-number{				
		height: .32rem;
		line-height: .32rem;
		border-radius: .2rem;
		padding:.04rem .32rem;
		margin: .08rem .1rem 0 0;
		background: rgba(0,0,0,0.4);
		font-size: .24rem;
	}
	.banner-icon{
		font-size: .24rem;
	}
</style>