<template>
	<view>
		<view class="goods_list">
			<view class="goods_item">
				<!-- 未渲染和适配 -->
				<image src="http://image1.suning.cn/uimg/b2c/newcatentries/0070134290-000000000149003877_1_800x800.jpg"></image>
				<view class="price">
					<text>￥2199</text>
					<text>￥2499</text>
				</view>
				<view class="name">
					spike 经典武士大马士革直刀(微型) 户外野营直刀 收藏礼品刀 饰品刀具
				</view>
			</view>
			<view class="goods_item">
				<image src="http://image1.suning.cn/uimg/b2c/newcatentries/0070134290-000000000149003877_1_800x800.jpg"></image>
				<view class="price">
					<text>￥2199</text>
					<text>￥2499</text>
				</view>
				<view class="name">
					spike 经典武士大马士革直刀(微型) 户外野营直刀 收藏礼品刀 饰品刀具
				</view>
			</view>
			<view class="goods_item">
				<image src="http://image1.suning.cn/uimg/b2c/newcatentries/0070134290-000000000149003877_1_800x800.jpg"></image>
				<view class="price">
					<text>￥2199</text>
					<text>￥2499</text>
				</view>
				<view class="name">
					spike 经典武士大马士革直刀(微型) 户外野营直刀 收藏礼品刀 饰品刀具
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		// 通过props来接收传递过来的数据
		props:['goods']
		,
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.goods_list {
		padding: 0 15rpx;
		display: flex;
		flex-wrap: wrap; //使商品自动换行
		justify-content: space-between;

		.goods_item {
			width: 355rpx;
			margin: 10rpx 0;
			padding: 15rpx;
			box-sizing: border-box;

			image {
				width: 80%;
				height: 350rpx;
			}

			.price {
				color: #ff0000;
				font-size: 36rpx;

				text:nth-child(2) {
					color: #ccc;
					font-size: 28rpx;
					margin-left: 17rpx;
					text-decoration: line-through;
				}
			}

			.name {
				font-size: 28rpx;
				line-height: 50rpx;
			}
		}
	}
</style>
