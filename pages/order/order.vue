<template>
	<view>
		<AHeader></AHeader>
		<view class="address">
			<view class="left-box">
				<view class="nickname">寻水的鱼</view>
				<view class="tip">默认</view>
			</view>
			<view class="center-box">
				<view class="row-line">
					<view>17600802300</view>
					<view>修改</view>
				</view>
				<view class="address-detail">北京市-朝阳区-大屯路，清和国际商户中心A座0928</view>
			</view>
		</view>
		<view class="split-border-lg"></view>
		<view class="order-pro">
			<view class="title">漫威农场</view>
			<view class="pro">
				<view class="pic-box">
					<image  style="width:180upx;height:180upx" src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2614863258,2946342685&fm=26&gp=0.jpg" mode="aspectFill"></image>
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
		<ACell class="split-bottom-border1" title="商品总额" content="¥10.00"></ACell>
		<ACell class="split-bottom-border1" title="活动减慢" content="¥10.00"></ACell>
		<ACell class="split-bottom-border1" title="优惠券" :link='true'></ACell>
		<ACell class="split-bottom-border1" title="运费" content="¥10.00"></ACell>
		<ACell  title="实付金额" content="¥10.00"></ACell>
		<view class="split-border-lg"></view>
		<view class="form-massage split-bottom-border1">
			<view class="title">留言</view>
			<view class="body">
				<input value="" placeholder="给卖家留言">
			</view>
		</view>
		<view class="footer-place"></view>
		<!-- 底部菜单 -->
		<view class="footer">
			<view class="price-box">
				<view>实付金额：</view>
				<view class="price">¥24.90</view>
			</view>
			<view class="btn">
				<view class="buy">
					<navigator url="/pages/pay/pay" hover-class="other-navigator-hover buy">
						立即支付
					</navigator>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import ACell from "../../components/ACell/ACell.vue"
import AHeader from "../../components/AHeader/AHeader.vue"
export default {
	components:{
		AHeader,
		ACell
	},
	data() {
		return {
			
		}
	},
	methods: {
		//返回上一页
		back() {
			uni.navigateBack();
		}
	}
}
</script>

<style lang='scss'>
.address{
	display: flex;
	flex: 0 1 0;
	flex-direction: row;
	
	color:$uni-text-color;
	font-size: $uni-font-size-base;
	padding: $uni-spacing-col-base 0;
	.left-box{
		flex: 0 1 0;
		padding-left: $uni-spacing-row-sm;
		white-space: nowrap;
		.nickname{
		}
		.tip{
			margin-top: $uni-spacing-col-base;
			font-size: $uni-font-size-sm;
			color: $uni-color-error;
			border:1px solid $uni-color-error;
			text-align: center;
			width: 70upx;
			box-sizing: border-box;
		}
	}
	.center-box{
		flex:1;
		padding:0 $uni-spacing-row-sm;
		.row-line{
			display: flex;
			flex-direction: row;
			justify-content: space-between;
		}
		.address-detail{
			line-height: 1.5;
			margin-top: $uni-spacing-col-sm;
		}
	}
}
.order-pro{
	color: $uni-text-color;
	padding: $uni-spacing-row-sm;
	.title{
		font-size: $uni-font-size-lg;
		color: $uni-text-color;
		padding:$uni-spacing-col-base 0;
	}
	.pro{
		display: flex;
		flex-direction: row;
		background: $uni-bg-color-grey;
		padding-top: $uni-spacing-col-sm;
		padding-bottom: $uni-spacing-col-sm;
		.pic-box{
			flex:0 0 200upx;
			width: 200upx;
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
}
.form-massage{
	display: flex;
	flex-direction: row;
	padding:  $uni-spacing-col-base $uni-spacing-row-base;
	.title{
		color:$uni-text-color;
		font-size: $uni-font-size-lg;
	}
	.body{
		flex:1;
		padding-left: $uni-spacing-row-sm;
		input{
			font-size: $uni-font-size-base;
		}
	}
}
.footer {
	position: fixed;
	bottom: 0upx;
	width: 100%;
	height: 99upx;
	border-top: solid 1upx #eee;
	background-color: #fff;
	z-index: 2;
	display: flex;
	justify-content: space-between;
	align-items: center;
	.price-box{
		white-space: nowrap;
		display: flex;
		padding: $uni-spacing-row-sm;
		font-size: $uni-font-size-base;
		color: $uni-text-color;
		.price{
			color: $uni-color-error;
		}
	}
	.icons {
		flex:1;
		display: flex;
		height: 80upx;
		margin-left: 10upx;
		.box {
			flex:1;
			width: 80upx;
			height: 80upx;
			display: flex;
			justify-content: center;
			flex-wrap: wrap;
			position: relative;
			&:first-of-type:after{
				content:"";
				display:block;
				position: absolute;
				width: 1px;
				height: 60upx;
				background:#f0f0f0;
				
				right: 0;
				top: 10upx;
			}
			.icon {
				font-size: 40upx;
				color: #828282;
			}
			.text {
				display: flex;
				justify-content: center;
				width: 100%;
				font-size: 22upx;
				color: #666;
			}
		}
	}
	.btn {
		flex:2;
		height:100%;
		display: flex;
		.joinCart,
		.buy {
			box-sizing: border-box;
			flex:1;
			height: 100%;
			color: #fff;
			display: flex;
			justify-content: center;
			align-items: center;
			text-align: center;
			font-size: 28upx;
		}
		.joinCart {
			background-color: #4eb87d;
			text-align: center;
			border-right: 1px solid #7fc19c;
		}
		.buy {
			background-color: #4eb87d;
			text-align: center;
		}
	}
}
</style>
