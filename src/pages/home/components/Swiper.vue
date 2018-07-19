<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
	    <!-- slides -->
	    <swiper-slide v-for="item in swiperList" :key="item.id">
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
	data() {
		return {
			swiperOption: {
				pagination: '.swiper-pagination',
				loop: true
			},
			swiperList: [{
				id: '0001',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/a1/41a802abfc4f0202.jpg_750x200_9f0cf69c.jpg'
			},{
				id: '0002',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/a1/e645466a5a1c9a02.jpg_750x200_9c489fbd.jpg'
			}]
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
		padding-bottom: 26.68%;
		/*上三句保持宽高比一直是31.25%*/
		/*height: 31.25%vw;*/
		background: #000;
	}
	.swiper-img{
		width: 100%;
	}
</style>