<template>
	<view>
		<view class="my-search-container" :style="{'background-color':bgColor }" @click="searchHandler()">
			<view class="my-search-box" :style="{'border-radius': radius + 'px'}">
				<!-- 图标可能出问题 -->
				<uni-icons type="search" size="17"></uni-icons>
				<text class="placeholder">搜索</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "my-search",
		// 可以动态更改背景颜色和圆角边框
		props: {
			bgColor: {
				type: String,
				default: '#C00000'
			},
			radius: {
				type: Number,
				default: 18
			}
		},
		data() {
			return {

			};
		},
		methods: {
			searchHandler() {
				console.log('done')
				// 触发外界通过 @click 绑定的 click 事件处理函数
				this.$emit('click')

			}
		}
	}
</script>

<style lang="scss">
	.my-search-container {
		height: 50px;
		// 垂直居中，左右留白
		display: flex;
		align-items: center;
		padding: 0 10px;

		.my-search-box {
			height: 36px;
			// 纯白
			background-color: #FFFFFF;
			// 占满整个宽度
			width: 100%;
			// 居中对齐
			display: flex;
			justify-content: center;
			align-items: center;

			.placeholder {
				font-size: 15px;
				margin-left: 5px;
			}
		}
	}
</style>
