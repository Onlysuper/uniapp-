<template>
	<view class="pay-page">
		<AHeader></AHeader> 
		<view class="pay-header">
			<view class="count-time">
				<view>支付剩余时间</view>
				<view class="row-line">
					<view class="item tip">10</view>
					<view class="item tip">1</view>
					<view class="item">:</view>
					<view class="item tip">5</view>
					<view class="item tip">9</view>
				</view>
			</view>
			<view class="pro">
				<view class="pic-box">
					<image  style="width:120upx;height:120upx" src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2614863258,2946342685&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
				<view class="pro-brief">
					<view>100%新疆黄胡萝卜新疆抓饭专用</view>
					<view class="row">
						规格：
						<view class="light">
							500g
						</view>
					</view>
					<view class="row">
						留言：
						<view class="light">
							需要一个礼盒
						</view>
					</view>
					<view class="row space-between">
						<view class="price">¥10.00</view>
						<view class="num">x2</view>
					</view>
				</view>
			</view>
		</view>
		<view class="pay-way">
			<view class="item split-bottom-border1">
				<view class="icon"></view>
				<view class="body">
					<view class="title">微信支付</view>
					<view class="describle">推荐微信用户使用</view>
				</view>
				<view><radio value="" /></view>
			</view>
			<view class="item split-bottom-border1">
				<view class="icon"></view>
				<view class="body">
					<view class="title">支付宝支付</view>
					<view class="describle">推荐支付宝用户使用</view>
				</view>
				<view><radio value="" /></view>
			</view>
			<view class="item split-bottom-border1">
				<view class="icon"></view>
				<view class="body">
					<view class="title">银联支付</view>
					<view class="describle">推荐银联用户使用</view>
				</view>
				<view><radio value="" /></view>
			</view>
		</view>
		<view class="footer">
			<view class="full-button">
				<navigator url="/pages/orderDetail/orderDetail">
					确认支付¥100.00
				</navigator>
			</view>
		</view>
	</view>
</template>

<script>
import AHeader from "../../components/AHeader/AHeader.vue"
export default {
	components:{
		AHeader
	},
	data() {
		return {
			
		}
	},
	methods: {
		
	}
}
</script>

<style lang='scss'>
.pay-page{
	height: 100vh;
	background: $uni-bg-color-hover;
}
.pay-header{
	background: $uni-bg-color-grey;
}
.count-time{
	color:$uni-text-color;
	font-size: $uni-font-size-base;
	text-align: center;
	padding: $uni-spacing-col-base;
	.row-line{
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		.item{
			flex: 0 0 20upx;
			&.tip{
				flex: 0 0 30upx;
				min-width: 40upx;
				background: $uni-text-color;
				color:#fff;
				border-radius: $uni-border-radius-sm;
				margin:3upx
			}
		}
	}
}
.pro{
	display: flex;
	flex-direction: row;
	background: $uni-bg-color-grey;
/* 	padding-top: $uni-spacing-col-sm;
	padding-bottom: $uni-spacing-col-sm; */
	padding: $uni-spacing-col-sm $uni-spacing-row-sm;
	.pic-box{
		flex:0 0 160upx;
		width: 160upx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.pro-brief{
		flex:1;
		font-size: $uni-font-size-base;
		padding:0 $uni-font-size-lg;
		.row{
			display: flex;
			flex-direction: row;
			&.space-between{
				justify-content: space-between;
			}
		}
		.light{
			color: $uni-text-color-placeholder
		}
		.price{
			color:$uni-color-error
		}
	}
}
.pay-way{
	background: #fff;
	font-size: $uni-font-size-base;
	color:$uni-text-color;
	.item{
		display: flex;
		flex-direction: row;
		padding: $uni-spacing-row-sm;
		align-items: center;
		justify-content: space-between;
		.icon{
			flex:0 0 100upx;
		}
		.body{
			flex:1;
		}
		.describle{
			font-size: $uni-font-size-sm;
			color:$uni-text-color-placeholder
		}
	}
}
.footer{
	padding: $uni-spacing-row-lg;
	margin-top: 80upx;
}
</style>
