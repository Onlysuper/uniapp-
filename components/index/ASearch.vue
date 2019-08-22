<template>
	<view class="top-search-box">
		<view class="local-box">
			<view class="">上海</view>
			<view></view>
		</view>
		<view class="input-box">
			<view class="input-back">
				<uni-icon type="search" size="30"></uni-icon>
				<input type="text" value="请输入关键字" />
			</view>
		</view>
		<view class="scan-box">
			<view class="icon">
				<image mode="widthFix" src="../../static/tabBars/item1.png"></image>
			</view>
			<view class="text">
				扫一扫
			</view>
		</view>
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		components: {uniIcon},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang='scss'>

.top-search-box{
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
	color:$color1;
	font-size: $uni-font-size-base;
	padding: $uni-spacing-row-sm 0;
	.local-box{
		white-space: nowrap;
		font-size: $uni-font-size-base;
		flex: 0 0 100upx;
		text-align: center;
	}
	.input-box{
		padding: 0 $uni-spacing-row-sm;
		flex:100%;
		.input-back{
			width: 100%;
			border-radius: 50upx;
			background:$back1;
			padding:5upx $uni-spacing-row-sm;
			box-sizing: border-box;
			display: flex;
			flex-direction: row;
			align-items: center;
		}
	}
	.scan-box{
		flex: 0 0 100upx;
		display: flex;
		flex-direction: column;
		align-items: center;
		.icon{
			width: 40upx;
			height: 40upx;
		}
		image{
			width: 100%;
		}
	}
}
</style>
