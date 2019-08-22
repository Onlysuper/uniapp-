<template>
	<view class="a-title">
		{{title}}
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		components: {uniIcon},
		props:['title'],
		data() {
			return {
				
				
			};
		}
	}
</script>

<style lang='scss'>
.a-title{
	text-align: center;
	color: #38383a;
	font-size: $uni-font-size-lg;
	font-weight: bold;
	padding: $uni-spacing-col-base $uni-spacing-row-base;
}
</style>
