<template>
	<view class="a-card">
		<view class="item" v-for="(item,index) in gridData" :key="index">
			<view class="img-box">
				<image style="width:100%;height:180upx;" mode="aspectFill"  :src="item.icon" />
			</view>
		</view>
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		name:'ACard',
		components: {uniIcon},
		props:['gridData'],
		data() {
			return {
				
				
			};
		}
	}
</script>

<style lang='scss'>
.a-card{
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: start;
	align-items: center;
	color:$color2;
	font-size: $uni-font-size-base;
	justify-content: space-between;
	.item{
		flex: 0 1 33.3%;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;
		min-width: 33.3%;
		box-sizing: border-box;
		padding: $uni-spacing-col-base;
		.img-box{
			box-shadow:0upx 2upx 5upx rgba(0,0,0,0.2);
			border-radius: 10upx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			overflow:hidden
		}
	}
}
</style>
