<template>
	<div>
	<div class="item"
		v-for="(item, index) of list"
		:key="index">
		<div class="item-title">
			<span class="item-title-icon"></span>
			{{item.title}}
		</div>
		<div class="item-children" v-if="item.children">
			<detail-list :list="item.children"></detail-list>
		</div>
	</div>
	</div>
</template>

<script>
export default {
	name: 'DetailList',
	props: {
		list: Array
	}	
}
</script>

<style scoped>
	.item-title{
		line-height: .8rem;
		font-size: .32rem;
		padding: 0 .2rem;
		border-bottom: 1px solid #f5f5f5;
	}
	.item-title-icon{
		display: inline-block;
	    position: relative;
	    width: .36rem;
	    height: .36rem;
	    top: .08rem;
	    left: .08rem;
	    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
	    margin-right: .1rem;
	    background-size: .4rem 3rem;
    }
    .item-children{
    	padding: 0 .2rem;
    }
</style>
