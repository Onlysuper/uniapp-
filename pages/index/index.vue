<template>
	<view class="my-page">
		<!-- #ifdef APP-PLUS -->
		<view class="top-space"></view>
		<!-- #endif -->
		<ASearch></ASearch>
		<view class="banner-container" style="border-radius:20upx;overflow:hidden;box-shadow:0upx 3upx 10upx #867f80">
			<uni-swiper-dot :info="info" :dotsStyles ="dotsStyles" :current="current" field="content" :mode="mode">
				<swiper class="swiper-box" @change="change">
					<swiper-item v-for="(item ,index) in info" :key="index" >
						<view class="swiper-item" style="{'text-align':'center'}">
						 <image style="width:100%; height:160px;background-color: #eeeeee;" mode="aspectFill" :src="item.img"></image>
						</view>
					</swiper-item>
				</swiper>
			</uni-swiper-dot>
		</view>
		
		<view>
			<AGrid :gridData="gridData"></AGrid>
		</view>
		<view class="split-border-lg"></view>
		<view>
			<navigator url="/pages/product/product" hover-class="other-navigator-hover">
			 	<ATitle title="定制精选"></ATitle>
			</navigator>
			<ACard :gridData="cardData"></ACard>
		</view>
	</view>
</template>

<script>
	import {uniSwiperDot} from "@dcloudio/uni-ui"
	import ASearch from "../../components/index/ASearch.vue"
	import AGrid from "../../components/AGrid/AGrid.vue"
	import ACard from "../../components/ACard/ACard.vue"
	import ATitle from "../../components/ATitle/ATitle.vue"
	export default {
		components: {
			uniSwiperDot,
			ASearch,
			AGrid,
			ACard,
			ATitle,
		},
		data() {
			return {
				dotsStyles :{
					width:'4',
					height:'4',
					selectedBackgroundColor:'rgba(0, 0, 0, 0.6)',
					selectedBorder:'rgba(0, 0, 0, 0.7)',
					bottom:'5'
				},
				info: [
					{
					content: '../static/logo.png',
					img:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2614863258,2946342685&fm=26&gp=0.jpg',
					},
					{
					content: '../static/logo.png',
					img:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566390166895&di=67c8bf6c4e48df7625c135c54be76c52&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01c4c357397ba06ac72580edf4c93e.jpg',
					},
					{
					content: '../static/logo.png',
					img:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566390258419&di=0e7c9ace2e742e913cc99bb6f185478f&imgtype=0&src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F016f265acc7b37a8012040296b97b3.jpg%402o.jpg',
					}
				],
				current: 0,
				mode: 'long',
				gridData:[
					{
						text:'菜谱',
						icon:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566390894447&di=4637790e5da40f91d54e2b20fe19f629&imgtype=0&src=http%3A%2F%2Fimg4.duitang.com%2Fuploads%2Fblog%2F201602%2F15%2F20160215111253_dAwNk.thumb.700_0.jpeg',
					},
					{
						text:'社区',
						icon:'../../static/logo.png',
					},
					{
						text:'定制',
						icon:'../../static/logo.png',
					},
					{
						text:'菜谱',
						icon:'../../static/logo.png',
					},
					{
						text:'社区',
						icon:'../../static/logo.png',
					},
					{
						text:'定制',
						icon:'../../static/logo.png',
					}
				],
				cardData:[
					{
						icon:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2008475314,2067335239&fm=26&gp=0.jpg',
					},
					{
						icon:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566985686&di=a5ba7510cda490e646cad30927e1dd59&imgtype=jpg&er=1&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201504%2F04%2F20150404H2030_rVmBU.jpeg',
					},
					{
						icon:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566985712&di=10904f7ccd60809698438a014a8953d6&imgtype=jpg&er=1&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fblog%2F201403%2F20%2F20140320083450_fdmTN.thumb.700_0.jpeg',
					},
					{
						icon:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2008475314,2067335239&fm=26&gp=0.jpg',
					},
					{
						icon:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566985686&di=a5ba7510cda490e646cad30927e1dd59&imgtype=jpg&er=1&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201504%2F04%2F20150404H2030_rVmBU.jpeg',
					},
					{
						icon:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1566985712&di=10904f7ccd60809698438a014a8953d6&imgtype=jpg&er=1&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fblog%2F201403%2F20%2F20140320083450_fdmTN.thumb.700_0.jpeg',
					},
				]
			}
		},
		onLoad() {

		},
		methods: {
			change(e) {
				this.current = e.detail.current;
			}
		}
	}
</script>

<style lang='scss'>
.swiper-item{
	text-align: center;

}
</style>
