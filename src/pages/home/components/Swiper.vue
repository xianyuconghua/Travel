<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showSwiper">
	    <!-- slides -->
	    <swiper-slide v-for="item in list" :key="item.id">
	    	<img class="swiper-img" :src="item.imgUrl"/>
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
  </div>
</template>

<script>
export default{
	name: 'HomeSwiper',
	props: {
		list: Array
	},
	data() {
		return {
			swiperOption: {
				pagination: '.swiper-pagination',
				loop: true,
				autoplay: 3000
			},
			// swiperList: [{
			// 	id: '0001',
			// 	imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/c6/44fce1467be17702.jpg_750x200_406f5fc3.jpg'
			// },{
			// 	id: '0002',
			// 	imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/a1/e645466a5a1c9a02.jpg_750x200_9c489fbd.jpg'
			// },{
			// 	id: '0003',
			// 	imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'
			// }]
		}
	},
	computed: {
		showSwiper () {
			return this.list.length
		}
	}
}
</script>

<style scoped>
	/*穿透，修改其他作用域的css*/
	.wrapper >>> .swiper-pagination-bullet-active{
		background: #fff; 
	}
	.wrapper{
		overflow: hidden;
		width: 100%;
		height: 0;
		padding-bottom: 31.25%;
		/*上三句保持宽高比一直是31.25%*/
		/*height: 31.25%vw;*/
		background: #000;
	}
	.swiper-img{
		width: 100%;
	}
</style>