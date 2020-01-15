<template>
	<view class="content">
		app端覆盖原生导航
		<button @tap="show">js覆盖原生show</button>
		<button @tap="hide">js覆盖原生hide</button>
		<button @tap="set">设置导航高度tabbar:50 nav:0</button>
	</view>
</template>

<script>
	import TabMask from '@/components/chunLei-modal/tabMask'
	
	export default {
		data() {
			return {
				tabMask:null
			}
		},
		onLoad() {
			let fn = ()=>{
				console.log('点击原生导航')
			}
			this.tabMask = new TabMask({opacity:0.6,fn})
		},
		async mounted() {
			
		},
		methods: {
			show(){
				this.tabMask.show(300)  //展示动画时间
			},
			hide(){
				this.tabMask.hide()
			},
			set(){
				let fn = ()=>{
					console.log('点击原生导航')
				}
				this.tabMask = new TabMask({
					tabbarHeight:50,
					navHeight:0,
					opacity:0.7,
					fn
				})
			}
		}
	}
</script>

<style lang="scss">
	.content{
		padding: 0 100rpx;
		
	}
	button{
		margin-top: 50rpx;
	}
</style>
