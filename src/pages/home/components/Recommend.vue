<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<router-link tag="li" class="item border-bottom" 
				v-for="item in list" 
				:key="item.id"
				:to="'/detail/' + item.id">
				<img class="item-img" :src="item.imgUrl" alt="">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</router-link>
		</ul>
	</div>
</template>

<script>
	export default{
		name: 'HomeRecommend',
		props: {
			list: Array
		},
		// data() {
		// 	return {				
		// 		recommendList: [{
		// 			id: '0001',
		// 			imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/cb/cbdf4d307562f6e6a3.water.jpg_200x200_b0adf528.jpg',
		// 			title: '园博园欢乐世界',
		// 			desc: '园博园欢乐世界水上乐园园博园欢乐世界园博园欢乐世界'
		// 		},{
		// 			id: '0002',
		// 			imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/cb/cbdf4d307562f6e6a3.water.jpg_200x200_b0adf528.jpg',
		// 			title: '园博园欢乐世界',
		// 			desc: '园博园欢乐世界水上乐园园博园欢乐世界园博园欢乐世界'
		// 		},{
		// 			id: '0003',
		// 			imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/cb/cbdf4d307562f6e6a3.water.jpg_200x200_b0adf528.jpg',
		// 			title: '园博园欢乐世界',
		// 			desc: '园博园欢乐世界水上乐园园博园欢乐世界园博园欢乐世界'
		// 		},{
		// 			id: '0004',
		// 			imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/cb/cbdf4d307562f6e6a3.water.jpg_200x200_b0adf528.jpg',
		// 			title: '园博园欢乐世界',
		// 			desc: '园博园欢乐世界水上乐园园博园欢乐世界园博园欢乐世界'
		// 		}]
		// 	}
		// }
	}
</script>

<style scoped>
	.title{
		line-height: .8rem;
		background:#f6f6f6;
		text-indent:.2rem;
		margin-top: .2rem;
		font-size: .32rem;
	}
	.item{
		display: flex;
		height: 1.9rem;
	}
	.item-img{
		width: 1.7rem;
		height: 1.7rem;
		padding: .1rem;
	}
	.item-info{
		flex: 1;
		padding: .1rem;
		min-width: 0;
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
		color: #ccc;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
	.item-button{
		line-height: .44rem;
		padding: 0 .2rem;
		background: #ff9300;
		border-radius: .06rem;
		color: #fff;
		margin-top: .2rem;
	}
</style>