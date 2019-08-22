<template>
	<!-- <view  class="my-page"> -->
	<view>
		<!-- #ifdef APP-PLUS -->
		<view class="top-space"></view> 
		<!-- #endif -->
		<view class="status" :style="{ opacity: afterHeaderOpacity }"></view>
		<view class="header">
			<!-- 头部 - 默认显示 -->
			<view class="before" :style="{ opacity: 1 - afterHeaderOpacity, zIndex: beforeHeaderzIndex }">
				<view class="back">
					<view class="icon xiangqian" @tap="back" v-if="showBack">
						<uni-icon type="arrowleft" size="28"></uni-icon>
					</view>
				</view> 
				<view class="middle"></view>
				<view class="icon-btn">
				</view>
			</view>
			<!-- 头部-滚动渐变显示 -->
			<view class="after" :style="{ opacity: afterHeaderOpacity, zIndex: afterHeaderzIndex }">
				<view class="back" >
					<uni-icon type="arrowleft" size="28" @tap="back" v-if="showBack">
						<view @tap="back" v-if="showBack"></view>
					</uni-icon>
					<!-- <view class="icon xiangqian" @tap="back" v-if="showBack"></view> -->
					</view>
				<view class="middle">
					<view v-for="(anchor,index) in anchorlist" :class="[selectAnchor==index ?'on':'']" :key="index" @tap="toAnchor(index)">{{anchor.name}}</view>
				</view>
				<view class="icon-btn">
				</view>
			</view>
		</view>
		<view class="swiper-box">
			<swiper circular="true" autoplay="true" @change="swiperChange">
				<swiper-item v-for="swiper in bannerList" :key="swiper.id">
					<image  :src="swiper.imgUrl" @tap="toSwiper(swiper)"></image>
				</swiper-item>
			</swiper>
			<view class="indicator">{{currentSwiper+1}}/{{bannerList.length}}</view>
		</view>
			<!-- 标题 价格 -->
		<view class="info-box goods-info">
			<view class="title">
				小萝卜
			</view>
			<view class="tip-box">
				小萝卜
			</view>
			<view class="price">
				¥10.00
			</view>
			<view class="old-price">
				¥29.00
			</view>
		</view>
		<view class="split-border-lg"></view>
		<Acell class="split-bottom-border1" title="规格" describe="100g"></Acell>
		<Acell class="split-bottom-border1" title="运费" describe="全场满100免运费"></Acell>
		<!-- <Acell class="split-bottom-border1" title="参数" :link='true'></Acell> -->
		<Acell class="split-bottom-border1" title="参数" describe="盒子包装"></Acell>
		<!-- 评价 -->
		<view class="info-box comments" id="comments">
			<view class="m-header">
				<view class="m-label">
					商品评价
				</view>
				<view class="m-detail">
					好评度 100%
				</view>
			</view>
			
			<view class="m-body" :key="1">
				<view class="img-box">
					<!-- <image v-if="item.anonymous==0" style="width:80upx;height:80upx" :src="item.headAddress" mode="aspectFit"></image> -->
					<image  style="width:80upx;height:80upx" src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2614863258,2946342685&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
				<view class="container">
					<view class="user-box">
						<view class="">
							<!-- <view v-if="item.anonymous==0" class="user-name">
								{{item.nickname}}
							</view> -->
							<view  class="user-name">
								匿名
							</view>
							<view class="time">
								2018-09-09
							</view>
						</view>
						<!-- <uni-rate size="18" :value="1"></uni-rate> -->
					</view>
					<view class="content">
						<view class="">
							哈哈哈哈哈啊好吃
							<!-- {{item.commentContent}} -->
						</view>
						<!-- <view class="m-reply">
							欢迎下次光临
						</view> -->
					</view>
				</view>
			</view>
		</view>
		<view class="split-border-lg"></view>
		<!-- 详情 -->
		<view class="description">
			<view class="m-header">
				<view class="m-label">
					商品详情
				</view>
			</view>
			<view class="m-body">
				<rich-text :nodes="descriptionStr"></rich-text>
			</view>
		</view>
		<view class="footer-place"></view>
		<!-- 底部菜单 -->
		<view class="footer">
			<view class="icons">
				<view class="box">
					图片
					<image style="width:38upx;height:100%" src="../../static/img/icon/goods_icon_house.png" mode="aspectFit"></image>
				</view>
			</view>
			<view class="btn">
				<view class="joinCart">
					<navigator class="back" url="/pages/order/order" hover-class="">
						加入购物车
					</navigator>
				</view>
				<view class="buy">
					<navigator class="back" url="/pages/order/order" hover-class="">
						立即购买
					</navigator>
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	import Acell from "../../components/ACell/ACell.vue"
	export default {
		components:{
			Acell,
			uniIcon
		},
		data() {
			return {
				//控制渐变标题栏的参数
				beforeHeaderzIndex: 11,//层级
				afterHeaderzIndex: 10,//层级
				beforeHeaderOpacity: 1,//不透明度
				afterHeaderOpacity: 0,//不透明度
				anchorlist:[],//导航条锚点
				// #ifndef MP
				showBack:true,
				// #endif
				selectAnchor:0,//选中锚点
				bannerList:[
					{imgUrl:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2614863258,2946342685&fm=26&gp=0.jpg'},
					{imgUrl:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566390166895&di=67c8bf6c4e48df7625c135c54be76c52&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01c4c357397ba06ac72580edf4c93e.jpg'}
				],
				currentSwiper: 0,//轮播图下标
				//商品描述html
				descriptionStr:"<div class='prodetail'>我是商品描述</div>"
			}
		},
		onReady(){
			this.calcAnchor();//计算锚点高度，页面数据是ajax加载时，请把此行放在数据渲染完成事件中执行以保证高度计算正确
		},
		
		onPageScroll(e) {
			//锚点切换
			this.selectAnchor = e.scrollTop>=this.anchorlist[2].top?2:e.scrollTop>=this.anchorlist[1].top?1:0;
			//导航栏渐变
			let tmpY = 375;
			e.scrollTop = e.scrollTop > tmpY ? 375 : e.scrollTop;
			this.afterHeaderOpacity = e.scrollTop * (1 / tmpY);
			this.beforeHeaderOpacity = 1 - this.afterHeaderOpacity;
			//切换层级
			this.beforeHeaderzIndex = e.scrollTop > 0 ? 10 : 11;
			this.afterHeaderzIndex = e.scrollTop > 0 ? 11 : 10;
		},
		methods: {
			//轮播图指示器
			swiperChange(event) {
				this.currentSwiper = event.detail.current;
			},
			//返回上一页
			back() {
				uni.navigateBack();
			},
			//计算锚点高度
			calcAnchor(){
				this.anchorlist=[
					{name:'主图',top:0},
					{name:'评价',top:0},
					{name:'详情',top:0}
				]
				let commentsView = uni.createSelectorQuery().select("#comments");
				commentsView.boundingClientRect((data) => {
					let statusbarHeight = 0;
					//APP内还要计算状态栏高度
					// #ifdef APP-PLUS
						statusbarHeight = plus.navigator.getStatusbarHeight()
					// #endif
					let headerHeight = uni.upx2px(100);
					this.anchorlist[1].top = data.top - headerHeight - statusbarHeight;
					this.anchorlist[2].top = data.bottom - headerHeight - statusbarHeight;
					
				}).exec();
			},
					//跳转锚点
			toAnchor(index){
				this.selectAnchor = index;
				uni.pageScrollTo({scrollTop: this.anchorlist[index].top,duration: 200});
			}
		}
	}
</script>

<style lang="scss">
.swiper-box {
	position: relative;
	width: 100%;
	height: 100vw;
	swiper {
		width: 100%;
		height: 100vw;
		swiper-item {
			image {
				width: 100%;
				height: 100vw;
			}
		}
	}
	.indicator{
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 0 25upx;
		height: 40upx;
		border-radius: 40upx;
		font-size: 22upx;
		position: absolute;
		bottom: 20upx;
		right: 20upx;
		color: #fff;
		background-color: rgba(0, 0, 0, 0.2);
	}
}
.description{
	background:#fff;
	font-size:$uni-font-size-base;
	.m-body{
		padding: $uni-spacing-col-base $uni-spacing-row-base;
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
	left: 0;
	.icons {
		flex:1;
		display: flex;
		height: 80upx;
		margin-left: 10upx;
		align-items: flex-start;
		.box {
			flex:1;
			width: 80upx;
			height: 80upx;
			display: flex;
			justify-content: center;
			flex-wrap: wrap;
			position: relative;
			align-items: center;
			justify-content: flex-start;
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
			display: flex;
			.back{
				padding: $uni-spacing-col-base $uni-spacing-row-lg;
				border-radius: 50upx;
				flex: 1;
				margin: 0 10upx;
			}
		}
		.joinCart {
			.back{
				background: $uni-color-warning;
			}
		}
		.buy {
			.back{
				background: $uni-color-success;
			}
		}
	}
}
.info-box {
	width: 100%;
	background-color: #fff;
	box-sizing: border-box;
}
// 评论start
.comments {
	.m-body{
		padding: $uni-spacing-col-base $uni-spacing-row-base;
		display: flex;
		flex-direction: row;
		border-bottom: 1px solid $uni-border-color;
		&:last-child{
			border:0;
		}
		.img-box{
			flex:0 1 80upx;
			height: 80upx;
			border-radius: 100%;
			overflow: hidden;
		}
		.container{
			flex:1;
			padding-left:20upx;
			.user-box{
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				color:$uni-text-color;
				font-size: $uni-font-size-base;
				.time{
					font-size: $uni-font-size-base;
					color:$uni-text-color;
				}
			}
			.content{
				padding-top: 10upx;
				font-size: $uni-font-size-base;
				.m-reply{
					background:#f7f7f7;
					color:$uni-text-color;
					font-size: $uni-font-size-base;
					padding:20upx;
					margin-top: 20upx;
				}
			}
		}
	}
}

.goods-info {
	text-align: center;
	padding:$uni-spacing-row-base 0;
	.title {
		font-size: $uni-font-size-lg;
		color:$uni-text-color;
	}
	.tip-box{
		margin-top: 10upx;
		width: 100%;
		text-align: center;
		color:$uni-text-color-placeholder;
		font-size: $uni-font-size-sm;
	}
	.price{
		font-size: $uni-font-size-lg;
		color:$uni-color-error;
	}
	.old-price{
		font-size: $uni-font-size-sm;
		color:$uni-text-color-grey;
		text-decoration: line-through;
	}
	.price-box{
		display: flex;
		flex-direction: row;
		align-items: center;
		color:$uni-text-color;
		margin-top: 10upx;
		.price{
			font-size: $uni-font-size-base;
			color:$uni-color-error;
			display: inline-block;
		}
		.oldprice{
			display: inline-block;
			margin-left: 20upx;
			font-size: $uni-font-size-base;
			color:$uni-text-color;
		}
		.num{
			display: inline-block;
			margin-left:30upx;
			padding-left: 20upx;
			font-size: $uni-font-size-base;
			border-left: 1px solid $uni-border-color;
		}
		.pickTime{
			flex-grow:1;
			text-align: right;
			color:$uni-color-error;
			font-size: $uni-font-size-base;
		}
	}
}
.header {
	width: 100%;
	height: 100upx;
	display: flex;
	align-items: center;
	position: fixed;
	top: 0;
	z-index: 10;
	/*  #ifdef  APP-PLUS  */
	top: var(--status-bar-height);
	/*  #endif  */
	.before,
	.after {
		width: 92%;
		padding: 0 4%;
		height: 100upx;
		display: flex;
		align-items: center;
		position: fixed;
		top: 0;
		/*  #ifdef  APP-PLUS  */
			top: var(--status-bar-height);
		/*  #endif  */

		.back {
			width: 125upx;
			height: 60upx;
			flex-shrink: 0;
			.icon {
				margin-left: -10%;
				width: 60upx;
				height: 60upx;
				display: flex;
				align-items: center;
				justify-content: center;
				font-size: 42upx;
			}
		}
		.middle {
			width: 100%;
			font-size: $uni-font-size-base;
		}
		.icon-btn {
			width: 125upx;
			height: 60upx;
			flex-shrink: 0;
			display: flex;
			.icon {
				&:first-child{
					margin-right: 5upx;
				}
				width: 60upx;
				height: 60upx;
				display: flex;
				justify-content: center;
				align-items: center;
				font-size: 42upx;
			}
		}
	}
	.before {
		.back {
			.icon {
				color: #fff;
				background-color: rgba(0, 0, 0, 0.2);
				border-radius: 100%;
			}
		}
		.icon-btn {
			.icon {
				color: #fff;
				background-color: rgba(0, 0, 0, 0.2);
				border-radius: 100%;
				
			}
		}
	}
	.after {
		background-color: #f1f1f1;
		.back {
			.icon {
				color: #666;
			}
		}
		.icon-btn {
			.icon {
				color: #666;
			}
		}
		.middle {
			font-size: 32upx;
			height: 90upx;
			display: flex;
			justify-content: center;
			align-items: center;
			view {
				padding: 0 3%;
				margin: 0 3%;
				display: flex;
				justify-content: center;
				align-items: center;
				&.on {
					margin-bottom: -4upx;
					color: #f47952;
					border-bottom: solid 4upx #f47952;
				}
			}
		}
	}
}
</style>
