<template>
	<view class="home">
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="item in swipers" :key="item.id">
				<image :src="item.img" mode=""></image>
			</swiper-item>
		</swiper>
		<!-- 导航区域 -->
		<view class="nav">
			<view class="nav_item" v-for="(item,index) in navs" :key="index" @click="navItemClick(item.path)">
				<view :class="item.icon"></view>
				<text>{{item.title}}</text>
			</view>

		</view>
		<!-- 推荐商品 -->
		<view class="hot_goods">
			<view class="tit">
				推荐商品
			</view>
			<good-list :goods="goods"></good-list>
		</view>
	</view>
</template>
<script>
	import goodList from '../../components/goods-list/good-list.vue'
	export default {
		data() {
			return {
				swipers: [],
				navs: [{
						icon: 'iconfont icon-ziyuan',
						title: '超市',
						path: '/pages/goods/goods'
					},
					{
						icon: 'iconfont icon-guanyuwomen',
						title: '联系我们',
						path: '/pages/contact/contact'
					},
					{
						icon: 'iconfont icon-tupian',
						title: '社区图片',
						path: '/pages/pics/pics'
					}, {
						icon: 'iconfont icon-shipin',
						title: '学习视频',
						path: '/pages/videos/videos'
					},
				]
			}
		},
		onLoad() {
			this.getSwipers()
		},
		components: {
			"good-list": goodList
		},
		methods: {
			// 获取轮播图的数据
			getSwipers() {
				console.log('获取轮播图的数据')
				uni.request({
					url: 'https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata',
					// 获取成功的数据
					success: res => {
						console.log(res)
						if (res.data.status == 0) {
							return uni.showToast({
								title: '获取数据失败'
							})
						}
						// 将数据保存到本地的数组里
						this.swipers = res.data.message
					}
				})
			},
			// 获取商品数据


			// 导航点击的处理函数  这里有问题，跳不过去
			navItemClick(url) {
				url.navigateTo({
					url
				})
			}
		}
	}
</script>

<style lang="scss">
	.home {
		swiper {
			width: 750rpx;
			height: 380rpx;

			image {
				height: 100%;
				width: 100%;
			}
		}

		.nav {
			display: flex;

			.nav_item {
				width: 25%;
				text-align: center;

				view {
					width: 120rpx;
					height: 120rpx;
					background: #16705c;
					border-radius: 60rpx;
					margin: 10px auto;
					line-height: 120rpx;
					color: #fff;
					font-size: 50rpx;
				}

				text {
					font-size: 30rpx;
				}
			}

		}

		.hot_goods {
			background: #eee;
			// margin塌陷 使用overflow: hidden;解决
			overflow: hidden;
			margin-top: 10px;

			.tit {
				height: 50px;
				line-height: 50px;
				color: #0f5041;
				text-align: center;
				letter-spacing: 20px;
				background: #fff;
				margin: 7rpx 0;
			}

		}
	}
</style>
