<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page, index) in pages" :key="index">
				<div class="icon" v-for="item in page" :key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgUrl" alt="">
					</div>
					<p class="desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
			<div class="swiper-pagination"  slot="pagination"></div>
		</swiper>
	</div>
</template>

<script>
	export default{
		name: 'HomeIcons',
		data() {
			return {
				swiperOption: {
					pagination: '.swiper-pagination'
				},
				iconList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '景点门票'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '滑雪季'
				},{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '泡温泉'
				},{
					id: '0004',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '动植园'
				},{
					id: '0005',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '景点门票'
				},{
					id: '0006',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '滑雪季'
				},{
					id: '0007',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '泡温泉'
				},{
					id: '0008',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '动植园'
				},{
					id: '0009',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '一日游'
				}]
			}
		},
		computed: {
			pages() {
				const pages = []
				this.iconList.forEach((item, index) => {
					const page = Math.floor(index / 8)
					if (!pages[page]) {
						pages[page] = []
					}
					pages[page].push(item)
				})
				return pages
			}
		}
	}
</script>

<style scoped>

	.icons >>> .swiper-pagination-bullets{
		bottom: 0;
	}
	.icons >>> .swiper-pagination-bullet-active{
		background: #33bfcb; 
	}
	.icons >>> .swiper-container{
		overflow: hidden;
		height: 0;
		padding-bottom: 54%;
	}
	.icon{
		float: left;
		width: 25%;
		padding-bottom: 25%;
		overflow: hidden;
		position: relative;
	}
	.icon-img{
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		bottom: .44rem;
		padding-top: .1rem;
		box-sizing: border-box;
	}
	.icon-img-content{
		height: 100%;
		display: block;
		margin: .1rem auto 0;
	}
	.icon .desc{
		position: absolute;
		left: 0;
		right: 0;
		bottom: 0;
		height: .44rem;
		line-height: .44rem;
		text-align: center;
		color:#212121;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
</style>