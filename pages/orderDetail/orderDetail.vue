<template>
	<view>
		<AHeader></AHeader>
		<view class="header">
			<view class="content">
				<view class="state-text">[农场跟踪]商品正在打包，准备发往上海市</view>
				<view class="time">2017.03.08</view>
			</view>
			<view class="icon-pic">
			</view>
		</view>
		<view class="address">
			<view class="icon">
				<uni-icon type="location" size="20"></uni-icon>
			</view>
			<view class="content">
				<view class="row-line">
					<view class="nickname">收货人：小丑鱼</view>
					<view class="phone">18738918919</view>
				</view>
				<view class="detail">收获地址：上海市徐州区域巴东A座1829</view>
			</view>
		</view>
		<view class="split-border-lg"></view>
		<!-- 商品图片详情 -->
		<view class="order-pro">
			<view class="title">漫威农场</view>
			<view class="pro">
				<view class="pic-box">
					<image  style="width:100upx;height:100upx" src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2614863258,2946342685&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
				<view class="pro-brief">
					<view>100%新疆黄胡萝卜新疆抓饭专用</view>
					<view class="row space-between">
						<view class="light">规格：500g</view>
						<view class="num">x2</view>
					</view>
				</view>
			</view>
			<view class="row message-box split-bottom-border1">
				<view>留言：</view>
				<view class="light-text">需要新增一个礼盒</view>
			</view>
			<view class="row pay-box">实付：<view class="price">¥99.80</view></view>
		</view>
		<view class="split-border-lg"></view>
		<!-- 支付信息 -->
		<view class="order-message">
			<view class="item">订单编号:<view class="describle">90903219039021</view></view>
			<view class="item">支付方式:<view class="describle">90903219039021</view></view>
			<view class="item">支付时间:<view class="describle">90903219039021</view></view>
			<view class="item">付款时间:<view class="describle">90903219039021</view></view>
			<view class="item">发货时间:<view class="describle">90903219039021</view></view>
		</view>
		<view class="split-border-lg"></view>
		<!-- 底部按钮 -->
		<view class="page-footer">
			<view class="time">
				还剩<view class="tip">20</view>天<view class="tip">0</view>时自动发货
			</view>
			<view class="but default">
				申请售后
			</view>
			<view class="but confirm">
				确认收获
			</view>
		</view>
	</view>
</template>

<script>
import uniIcon from "@/components/uni-icon/uni-icon.vue"
import AHeader from "../../components/AHeader/AHeader.vue"
	export default {
		components:{
			uniIcon,
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

<style lang="scss">
.header{
	background:$uni-color-success;
	display: flex;
	flex-direction: row;
	padding:$uni-spacing-col-base $uni-spacing-row-base;
	.content{
		font-size: $uni-font-size-base;
		color:$uni-text-color-inverse;
		flex:1;
		.time{
			margin-top: $uni-spacing-col-base;
			color:rgba(255,255,255,0.8)
		}
	}
	.icon-pic{
		flex:1;
	}
}
.address{
	display: flex;
	flex-direction: row;
	color:$uni-text-color;
	padding:$uni-spacing-col-base $uni-spacing-row-base;
	.icon{
		flex: 0 0 50upx;
	}
	.content{
		font-size: $uni-font-size-base;
		flex:1;
		.row-line{
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: space-between;
		}
		.detail{
			color:$uni-text-color-placeholder;
			font-size:$uni-font-size-sm;
			margin-top: $uni-spacing-col-sm;
		}
	}
}
.order-pro{
	color: $uni-text-color;
	padding: $uni-spacing-row-sm;
	font-size: $uni-font-size-base;
	.title{
		font-size: $uni-font-size-lg;
		color: $uni-text-color;
		padding:$uni-spacing-col-base 0;
	}
	.light{
			color: $uni-text-color-placeholder
	}
	.price{
		color:$uni-color-error
	}
	.pro{
		display: flex;
		flex-direction: row;
		background: $uni-bg-color-grey;
		padding-top: $uni-spacing-col-sm;
		padding-bottom: $uni-spacing-col-sm;
		.pic-box{
			flex:0 0 120upx;
			width: 120upx;
			display: flex;
			align-items: center;
			justify-content: center;
			image{
				width: 100%;
				height:100%;
			}
		}
		.pro-brief{
			flex:1;
			padding:0 $uni-font-size-lg;
			.row{
				display: flex;
				flex-direction: row;
				&.space-between{
					justify-content: space-between;
				}
			}
		}
	}
	.row{
		display: flex;
		padding: $uni-spacing-col-base 0;
	}
	.pay-box{
		    justify-content: flex-end;
	}
}
.order-message{
	font-size:$uni-font-size-base;
	padding: $uni-spacing-row-sm;
	.item{
		display: flex;
		padding: $uni-spacing-col-sm 0;
		.describle{
			color: $uni-text-color-placeholder;
			padding-left: $uni-spacing-row-sm;
		}
	}
	
}
.page-footer{
	display: flex;
	font-size: $uni-font-size-base;
	color:$uni-text-color;
	padding: 0 $uni-spacing-row-sm;
	.time{
		display: flex;
		align-items: center;
		.tip{
			color: $uni-color-error;
			font-size: $uni-font-size-lg;
		}
	}
	.but{
		padding: $uni-spacing-col-sm $uni-spacing-row-sm;
		border-radius: $uni-border-radius-lg;
		&.default{
			border:1px solid $uni-border-color;
		}
		&.confirm{
			border:1px solid $uni-color-success;
			background: $uni-color-success;
			color:$uni-text-color-inverse
		}
	}
}
</style>
