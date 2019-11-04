<template>
	<view class="content">
		<button @tap="tapBtn('default')">默认</button>
		<button @tap="tapBtn('select')">单选</button>
		<button @tap="tapBtn('multiSelect')">多选</button>
		<button @tap="tapBtn('advert')">广告</button>
		<button @tap="tapBtn('share')">分享</button>
		<button @tap="tapBtn('input')">输入框</button>
		<button @tap="tapBtn('custom')">自定义</button>
		<chunLei-modal v-model="value" :mData="data" :type="type" @onConfirm="onConfirm" @onCancel="onCancel" navMask>
			<div class="custom-view" @tap.stop>
				<div class="hongbao">
					<div class="top">该红包已超过24小时。如已领取,可在“红包记录”中查看</div>
					<div class="bottom">查看领取详情></div>
				</div>
				<image class="cancel" @tap.stop="value=false" src="../../static/close.png"></image>
			</div>
		</chunLei-modal>
	</view>
</template>

<script>
	import chunLeiModal from '@/components/chunLei-modal/chunLei-modal.vue'
	export default {
		components:{
			chunLeiModal
		},
		data() {
			return {
				value:false,
				type:'default',
				data:{},
				defaultData:{title:'提示',content:'这是一个模态弹窗',cancelText:'cancel',confirmColor:'#3CC51F'},
				selectData:[{title:'拍摄',content:'照片或视频',icon:'../../static/shoot.png'},{title:'从照片选择'}],
				multiSelectData:[{title:'拍摄',icon:'../../static/shoot.png',radioColor:'red',flag:false},{title:'从照片选择',flag:true}],
				advertData:{src:'../../static/advert.jpg',width:'600rpx',height:'350rpx'},
				shareData:[
					{title:'朋友圈',icon:'../../static/pengyouquan.png'},
					{title:'微信好友',icon:'../../static/weixinhaoyou.png'},
					{title:'微博',icon:'../../static/weibo.png'},
					{title:'QQ好友',icon:'../../static/QQhaoyou.png'},
					{title:'QQ空间',icon:'../../static/QQkongjian.png'},
				],
				inputData:{
					title:'登录',
					content:[
						{title:'手机号',content:'',type:'number',placeholder:'请输入手机号'},
						{title:'密码',content:'',type:'password',placeholder:'请输入密码'},
					]
				}
			
			}
		},
		onLoad() {
			
		},
		async mounted() {
			
		},
		methods: {
			onConfirm(e){
				switch(this.type){
					case 'default':
						uni.showToast({title:'确认',icon:'none'})
						break;
					case 'select':
						uni.showToast({title:e.title,icon:'none'})
						break;
					case 'advert':
						uni.showToast({title:'广告',icon:'none'})
						break;
					case 'share':
						uni.showToast({title:e.title,icon:'none'})
						break;
					case 'input':
						console.log(e)
						break;
					case 'multiSelect':
						console.log(e)
						break;
				}
			},
			onCancel(){
				uni.showToast({title:'取消',icon:'none'})
			},
			tapBtn(type){
				this.type = type
				this.value = !this.value
				switch(this.type){
					case 'default':
						this.data = this.defaultData
						break;
					case 'select':
						this.data = this.selectData
						break;
					case 'advert':
						this.data = this.advertData
						break;
					case 'share':
						this.data = this.shareData
						break;
					case 'input':
						this.data = this.inputData
						break;
					case 'multiSelect':
						this.data = this.multiSelectData
						break;
				}
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
	.custom-view{
		overflow: hidden;
		
		display: flex;
		flex-direction: column;
		align-items: center;
		.hongbao{
			width: 500rpx;
			height: 700rpx;
			border-radius: 6rpx;
			background: #F35543;
			.top{
				text-align: center;
				padding: 100rpx 80rpx 0 ;
				height: 400rpx;
				background: #F45E4D;
				color: #FEDCAC;
				font-szie:30px;
				border-bottom-right-radius: 60% 100rpx;
				border-bottom-left-radius: 60% 100rpx;
				box-shadow: 0 1px 4px #717171;
			}
			.bottom{
				margin-top: 80rpx;
				color: #FDC69B;
				text-align: center;
			}
		}
		.cancel{
			margin-top: 100rpx;
			width: 60rpx;
			height: 60rpx;
		}
	}
</style>
