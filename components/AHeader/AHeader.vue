<template>
	<view>
		<view class="header" @tap="back">
			<view class="">
				<uni-icon type="arrowleft" size="30"></uni-icon>
			</view>
		</view>
		<view class="header-place"></view>
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		components: {uniIcon},
		data() {
			return {
				
			};
		},
		methods:{
			//返回上一页
			back() {
				uni.navigateBack();
			}
		}
	}
</script>

<style lang="scss">
.header{
	height:$header-height;
	background:$uni-color-success;
	color:#fff;
	position: fixed;
	width: 100%;
	padding: $uni-spacing-col-sm $uni-spacing-row-sm;
	box-sizing: border-box;
	display: flex;
	flex-direction: column;
	align-items: flex-start;
	justify-content: flex-end;
}
</style>
