<template>
	<view class="a-grid">
		<view class="item" v-for="(item,index) in gridData" :key="index">
			<view class="icon">
				<image style="width:60upx;height:60upx;" mode="aspectFill"  :src="item.icon" />
			</view>
			<view class="text">
				{{item.text}}
			</view>
		</view>
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		components: {uniIcon},
		props:['gridData'],
		data() {
			return {
				
				
			};
		}
	}
</script>

<style lang='scss'>
.a-grid{
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: start;
	align-items: center;
	color:$color2;
	font-size: $uni-font-size-base;
	margin: $uni-spacing-row-lg;
	.item{
		flex: 0 1 25%;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;
		min-width: 25%;
		box-sizing: border-box;
		padding: $uni-spacing-col-base
	}
}
</style>
