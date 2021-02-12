<template>
	<view>
		<good-list></good-list>
	</view>
</template>

<script>
	import goodList from '../../components/goods-list/good-list.vue'
	export default {
		data() {
			return {
				
			}
		},
		components:{"goods-list":goodList},
		methods: {
			// 此处有获取商品列表的数据的方法
		}
	}
</script>

<style>

</style>
