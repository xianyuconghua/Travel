<template>
	<div>
		<div class="title">周末去哪儿</div>
		<ul>
			<li class="item border-bottom" v-for="item in recommendList" :key="item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgUrl" alt="">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default{
		name: 'HomeWeekend',
		data() {
			return {				
				recommendList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1507/c7/dae0666d416570.jpg_r_640x214_8ed0c3f1.jpg',
					title: '水上项目TOP10',
					desc: '水上嘉年华，清爽凉“一夏”'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1507/c7/dae0666d416570.jpg_r_640x214_8ed0c3f1.jpg',
					title: '水上项目TOP10',
					desc: '水上嘉年华，清爽凉“一夏”'
				},{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1507/c7/dae0666d416570.jpg_r_640x214_8ed0c3f1.jpg',
					title: '水上项目TOP10',
					desc: '水上嘉年华，清爽凉“一夏”'
				},{
					id: '0004',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1507/c7/dae0666d416570.jpg_r_640x214_8ed0c3f1.jpg',
					title: '水上项目TOP10',
					desc: '水上嘉年华，清爽凉“一夏”'
				}]
			}
		}
	}
</script>

<style scoped>
	li{
		border-bottom: 4px solid #f6f6f6;
	}
	.title{
		line-height: .8rem;
		background:#f6f6f6;
		text-indent:.2rem;
		font-size: .32rem;
	}
	.item-img-wrapper{
		overflow: hidden;
		height: 0;
		padding-bottom: 34%;
	}
	.item-img{
		width: 100%;
	}
	.item-info{
		padding:.1rem .2rem .2rem;
	}
	.item-title{
		line-height: .54rem;
		font-size: .32rem;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
	.item-desc{
		line-height: .4rem;
		color: #999;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
</style>