<template>
<div>
	<router-link tag="div" to="/" class="header-abs" v-show="showAbs">
		<span class="iconfont header-abs-back">&#xe624;</span>
	</router-link>

	<div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
		<router-link to='/'>
			<div class="iconfont header-fixed-back">&#xe624;</div>
		</router-link>
		景点详情		
	</div>
</div>
</template>

<script>
export default {
	name: 'DetailHeader',
	data () {
		return {
			showAbs: true,
			opacityStyle: {
				opacity: 0
			}
		}
	},
	methods: {
		handleScroll () {
			console.log('scroll')
			//console.log(ocument.documentElement.scrollTop)
			const top = document.documentElement.scrollTop
			 if (top > 60) {
				let opacity = top / 140
				opacity = opacity > 1 ? 1 : opacity
				this.opacityStyle = { opacity }
				this.showAbs = false
			}else{
				this.showAbs = true
			}
		}
	},
	activated () {
		window.addEventListener('scroll', this.handleScroll)
	},
	deactivated () {
		window.removeEventListener('scroll', this.handleScroll)
	}
	
}
</script>

<style scoped>
.header-abs{
	width: .72rem;
	height: .72rem;
	border-radius: .36rem;
	background: rgba(0, 0, 0, .6);
	position: absolute;
	left: .2rem;
	top: .2rem;
	text-align: center;
	line-height: .72rem;
}
.header-abs-back{
	color: #fff;
	font-size: .36rem;
}

.header-fixed{
	height: .86rem;
	line-height: .86rem;
	text-align: center;
	color: #fff;
	background: #00bcd4;
	font-size: .32rem;
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
	z-index: 2;
}
.header-fixed-back{
	width: .64rem;
	text-align: center;
	position: absolute;
	left: 0;
	top: 0;
	font-weight: 900;
	color: #fff;
}
</style>
