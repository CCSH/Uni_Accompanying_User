<template>
	<view class="page flex-col">
		<view class="box_1 flex-col">
			<view class="box_4 flex-col">
				<view class="box_5 flex-col">
					<view class="block_1 flex-row">
						<view class="text-wrapper_3 flex-col">
							<text class="text_6">1</text>
						</view>
						<image class="image_4" referrerpolicy="no-referrer" src="/static/point_line.png" />
						<view class="text-wrapper_4 flex-col">
							<text class="text_7">2</text>
						</view>
						<image class="image_5" referrerpolicy="no-referrer" src="/static/point_line.png" />
						<view class="text-wrapper_5 flex-col">
							<text class="text_8">3</text>
						</view>
						<image class="image_6" referrerpolicy="no-referrer" src="/static/point_line.png" />
						<view class="text-wrapper_6 flex-col">
							<text class="text_9">4</text>
						</view>
					</view>
					<view class="text-wrapper_7 flex-row justify-between">
						<text class="text_10">填写订单</text>
						<text class="text_11">在线支付</text>
						<text class="text_12">服务中</text>
						<text class="text_13">服务完成</text>
					</view>
				</view>
				<view class="box_6 flex-row" @click="showServe">
					<view class="group_4 flex-col"></view>
					<text class="text_14">检查预约</text>
					<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/more_lv@2x.png" />
					<text class="text_15">服务项目</text>
				</view>
			</view>
			<view class="box_7 flex-col">
				<view class="group_5 flex-row">
					<view class="group_6 flex-col"></view>
					<text class="text_16">服务项目</text>
				</view>
				<view class="group_7 flex-row">
					<text class="paragraph_1">
						就诊医院
						<br />
						就诊科室
						<br />
						就诊时间
					</text>
					<view class="text-wrapper_8 flex-col">
						<text class="paragraph_2">
							成都416医院
							<br />
						</text>
						<text class="paragraph_3">
							请选择就诊室
							<br />
						</text>
						<text class="paragraph_3">
							请选择就诊时间
							<br />
						</text>
					</view>
					<view class="image-wrapper_1 flex-col">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
						<image class="thumbnail_8" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
						<image class="thumbnail_9" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
					</view>
				</view>
				<image class="image_7" referrerpolicy="no-referrer" />
				<image class="image_8" referrerpolicy="no-referrer" />
			</view>
			<view class="box_8 flex-col">
				<view class="group_8 flex-row">
					<text class="text_17">共计</text>
					<view class="text-wrapper_9">
						<text class="text_18">￥</text>
						<text class="text_19">148</text>
						<text class="text_20">.00</text>
					</view>
					<view class="text-wrapper_10 flex-col">
						<text class="text_21">立即下单</text>
					</view>
				</view>
				<view class="image-wrapper_2 flex-row"></view>
			</view>
			<view class="box_9 flex-col">
				<view class="box_10 flex-col">
					<view class="box_11 flex-row">
						<view class="group_9 flex-col"></view>
						<text class="text_22">就诊信息</text>
					</view>
					<view class="box_12 flex-row">
						<text class="text_23">就诊人</text>
						<text class="text_24">请选择就诊人</text>
						<image class="thumbnail_10" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
					</view>
				</view>
				<text class="text_25">注意事项</text>
				<text class="paragraph_4">
					1.仅支持当地医院的服务。
					<br />
					2.下单成功后，因个人原因，就诊时间前12小时内取消订单-扣除5%服务费用，就诊时间前6小时内取消订单-扣除10%服务费用，就诊时间前3小时内取消订单-扣除50%服务费用，就诊时间前2小时内取消订单-扣除100%服务费用。
				</text>
				<view class="image-text_1 flex-row justify-between">
					<image class="box_13 flex-col" :src="isAgreement ? '/static/fangkuai_h@2x.png' : '/static/fangkuai_n@2x.png'" mode="scaleToFill" @click="isAgreement = !isAgreement" />
					<view class="text-group_1 flex-col">
						<text class="text_26">我已认真阅读并同意预约相关</text>
						<text class="text_27" @click="showAgreement">《服务条款同意书》</text>
					</view>
				</view>
			</view>
		</view>

		<!-- 悬浮 -->
		<drag-button @btnClick="gotoService" :isDock="true" :existTabBar="true"></drag-button>
		<!-- 弹窗 -->
		<uni-popup ref="popup_serve" type="bottom" :safe-area="false">
			<view class="pop_content">
				<view class="box_1 flex-col">
					<view class="block_3 flex-row justify-between">
						<view class="box_2 flex-col"></view>
						<image class="thumbnail_1" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_serve.close()" />
						<text class="text_1">服务项目</text>
					</view>
					<view class="block_4 flex-row" @click="serveIndex = 0">
						<image :src="serveIndex == 0 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_1 flex-row justify-between">
							<view class="box_4 flex-col"></view>
							<view class="text-group_1 flex-col">
								<text class="text_2">全程陪诊</text>
								<text class="text_3">全程陪同服务，手续代办服务</text>
							</view>
						</view>
						<view class="image-text_2 flex-col">
							<image class="thumbnail_2" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_2">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_5 flex-row" @click="serveIndex = 1">
						<image :src="serveIndex == 1 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_3 flex-row justify-between">
							<view class="box_5 flex-col"></view>
							<view class="text-group_3 flex-col">
								<text class="text_4">代办买药</text>
								<text class="text_5">人工排队代买药服务</text>
							</view>
						</view>
						<view class="image-text_4 flex-col">
							<image class="thumbnail_4" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_4">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_6 flex-row" @click="serveIndex = 2">
						<image :src="serveIndex == 2 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_5 flex-row justify-between">
							<view class="group_1 flex-col"></view>
							<view class="text-group_5 flex-col">
								<text class="text_6">代办问诊</text>
								<text class="text_7">代客户到机构咨询及代开检查单服务</text>
							</view>
						</view>
						<view class="image-text_6 flex-col">
							<image class="thumbnail_5" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_6">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_7 flex-row" @click="serveIndex = 3">
						<image :src="serveIndex == 3 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_7 flex-row justify-between">
							<view class="block_9 flex-col"></view>
							<view class="text-group_7 flex-col">
								<text class="text_8">送取结果</text>
								<text class="text_9">送/取结果快递到家服务，服务仅限当…</text>
							</view>
						</view>
						<view class="image-text_8 flex-col">
							<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_8">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_10 flex-row" @click="serveIndex = 4">
						<image :src="serveIndex == 4 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_9 flex-row justify-between">
							<view class="section_2 flex-col"></view>
							<view class="text-group_9 flex-col">
								<text class="text_10">尊享服务</text>
								<text class="text_11">组合套餐项目升级包</text>
							</view>
						</view>
						<view class="image-text_10 flex-col">
							<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_10">详情</text>
						</view>
					</view>
					<!-- <image class="image_2" referrerpolicy="no-referrer" src="" /> -->
				</view>
			</view>
		</uni-popup>
	</view>
</template>
<script>
import dragButton from '@/components/drag-button/drag-button.vue'

export default {
	components: {
		dragButton,
	},
	data() {
		return {
			isAgreement: true,
			serveIndex: 0,
			constants: {},
		}
	},
	methods: {
		gotoService() {
			uni.showToast({
				title: '咨询客服',
				icon: 'none',
				duration: 1000,
			})
		},
		showAgreement() {
			uni.navigateTo({ url: '/pagesA/pages/privacy_agreement/privacy_agreement' })
		},
		showServe() {
			this.$refs.popup_serve.open()
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	overflow: hidden;
	.box_1 {
		background-color: rgba(246, 246, 246, 1);
		position: relative;
		.group_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.section_1 {
				margin: 0 18rpx 0 2rpx;
				.text-wrapper_2 {
					width: 108rpx;
					height: 34rpx;
					overflow-wrap: break-word;
					font-size: 0;
					letter-spacing: -0.2800000011920929px;
					font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
					font-weight: normal;
					text-align: right;
					white-space: nowrap;
					line-height: 34rpx;
					.text_4 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_5 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.thumbnail_4 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_5 {
					width: 30rpx;
					height: 22rpx;
					margin: 2rpx 0 10rpx 10rpx;
				}
				.image_3 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.section_2 {
				margin-top: 30rpx;
				.thumbnail_3 {
					width: 24rpx;
					height: 40rpx;
					margin-bottom: 20rpx;
				}
				.text_3 {
					overflow-wrap: break-word;
					color: rgba(255, 255, 255, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: right;
					white-space: nowrap;
					line-height: 48rpx;
					margin-left: 244rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 136rpx;
				}
			}
		}
		.box_4 {
			padding: 24rpx 24rpx 22rpx 24rpx;
			.box_5 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				padding: 30rpx 24rpx 30rpx 22rpx;
				.block_1 {
					margin: 0 26rpx 0 30rpx;
					.text-wrapper_3 {
						background-color: rgba(81, 187, 164, 1);
						border-radius: 50%;
						padding: 6rpx 20rpx 6rpx 20rpx;
						.text_6 {
							overflow-wrap: break-word;
							color: rgba(255, 255, 255, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.image_4 {
						width: 42rpx;
						height: 2rpx;
						margin: 28rpx 0 22rpx 46rpx;
					}
					.text-wrapper_4 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin-left: 50rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_7 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.image_5 {
						width: 54rpx;
						height: 2rpx;
						margin: 28rpx 0 22rpx 46rpx;
					}
					.text-wrapper_5 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin-left: 26rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_8 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.image_6 {
						width: 54rpx;
						height: 2rpx;
						margin: 28rpx 0 22rpx 30rpx;
					}
					.text-wrapper_6 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin-left: 44rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_9 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
				}
				.text-wrapper_7 {
					width: 656rpx;
					margin-top: 12rpx;
					.text_10 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_12 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_13 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
			}
			.box_6 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				position: relative;
				margin-top: 28rpx;
				padding: 34rpx 32rpx 32rpx 50rpx;
				.group_4 {
					background-color: rgba(165, 229, 215, 1);
					border-radius: 5px;
					width: 80rpx;
					height: 20rpx;
					margin-top: 22rpx;
				}
				.text_14 {
					overflow-wrap: break-word;
					color: rgba(81, 187, 164, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 398rpx;
				}
				.thumbnail_6 {
					width: 6rpx;
					height: 16rpx;
					margin: 12rpx 0 14rpx 24rpx;
				}
				.text_15 {
					position: absolute;
					left: 26rpx;
					top: 32rpx;
					overflow-wrap: break-word;
					color: rgba(69, 69, 69, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
		}
		.box_7 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			align-self: center;
			margin-top: -2rpx;
			width: 702rpx;
			position: relative;
			padding: 32rpx 32rpx 14rpx 24rpx;
			.group_5 {
				position: relative;
				margin: 0 508rpx 0 2rpx;
				padding: 24rpx 32rpx 4rpx 24rpx;
				.group_6 {
					background-color: rgba(165, 229, 215, 1);
					border-radius: 5px;
					width: 80rpx;
					height: 20rpx;
				}
				.text_16 {
					position: absolute;
					left: 0;
					top: 0;
					overflow-wrap: break-word;
					color: rgba(69, 69, 69, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
			.group_7 {
				margin-top: 32rpx;
				.paragraph_1 {
					width: 112rpx;
					height: 324rpx;
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 108rpx;
				}
				.text-wrapper_8 {
					width: 196rpx;
					// height: 324rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: right;
					line-height: 108rpx;
					margin-left: 308rpx;
					.paragraph_2 {
						width: 196rpx;
						// height: 324rpx;
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 28rpx;
						font-weight: normal;
						// text-align: left;
						// line-height: 108rpx;
					}
					.paragraph_3 {
						width: 196rpx;
						// height: 324rpx;
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						// text-align: left;
						// line-height: 108rpx;
					}
				}
				.image-wrapper_1 {
					margin: 44rpx 0 46rpx 24rpx;
					.thumbnail_7 {
						width: 6rpx;
						height: 16rpx;
					}
					.thumbnail_8 {
						width: 6rpx;
						height: 16rpx;
						margin-top: 94rpx;
					}
					.thumbnail_9 {
						width: 6rpx;
						height: 16rpx;
						margin-top: 92rpx;
					}
				}
			}
			.image_7 {
				position: absolute;
				left: 24rpx;
				top: 212rpx;
				width: 652rpx;
				height: 2rpx;
				background: #e7e7e7;
			}
			.image_8 {
				position: absolute;
				left: 24rpx;
				top: 328rpx;
				width: 652rpx;
				height: 2rpx;
				background: #e7e7e7;
			}
		}
		.box_8 {
			background-color: rgba(254, 254, 254, 1);
			margin-top: 586rpx;
			padding: 10rpx 32rpx 18rpx 40rpx;
			.group_8 {
				.text_17 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 20rpx;
				}
				.text-wrapper_9 {
					width: 118rpx;
					height: 50rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					line-height: 34rpx;
					margin: 14rpx 0 12rpx 12rpx;
					.text_18 {
						height: 50rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 176, 1);
						font-size: 24rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						line-height: 34rpx;
					}
					.text_19 {
						height: 50rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 176, 1);
						font-size: 36rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_20 {
						height: 50rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 176, 1);
						font-size: 24rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						line-height: 34rpx;
					}
				}
				.text-wrapper_10 {
					background-color: rgba(80, 186, 176, 1);
					border-radius: 19px;
					margin-left: 252rpx;
					padding: 22rpx 76rpx 20rpx 76rpx;
					.text_21 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
			}
			.image-wrapper_2 {
				margin: 42rpx 208rpx 0 202rpx;
				.image_9 {
					width: 268rpx;
					height: 10rpx;
				}
			}
		}
		.box_9 {
			position: absolute;
			left: 0;
			top: 790rpx;
			width: 750rpx;
			height: 588rpx;
			padding: 22rpx 24rpx 16rpx 24rpx;
			.box_10 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				padding: 26rpx 32rpx 6rpx 24rpx;
				.box_11 {
					position: relative;
					margin: 0 508rpx 0 2rpx;
					padding: 24rpx 32rpx 4rpx 24rpx;
					.group_9 {
						background-color: rgba(165, 229, 215, 1);
						border-radius: 5px;
						width: 80rpx;
						height: 20rpx;
					}
					.text_22 {
						position: absolute;
						left: 0;
						top: 0;
						overflow-wrap: break-word;
						color: rgba(69, 69, 69, 1);
						font-size: 34rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 48rpx;
					}
				}
				.box_12 {
					margin-top: 32rpx;
					.text_23 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 108rpx;
					}
					.text_24 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: center;
						line-height: 108rpx;
						margin-left: 364rpx;
					}
					.thumbnail_10 {
						width: 6rpx;
						height: 16rpx;
						margin: 44rpx 0 48rpx 24rpx;
					}
				}
			}
			.text_25 {
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 28rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: center;
				white-space: nowrap;
				line-height: 40rpx;
				margin: 24rpx 570rpx 0 20rpx;
			}
			.paragraph_4 {
				width: 650rpx;
				height: 170rpx;
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 24rpx;
				font-weight: normal;
				text-align: left;
				line-height: 34rpx;
				margin: 6rpx 34rpx 0 18rpx;
			}
			.image-text_1 {
				width: 368rpx;
				margin: 20rpx 314rpx 0 20rpx;
				.box_13 {
					background-color: rgba(255, 255, 255, 1);
					// border-radius: 4px;
					width: 40rpx;
					height: 40rpx;
					// border: 1px solid rgba(153, 153, 153, 1);
					margin-bottom: 30rpx;
					background-size: cover;
				}
				.text-group_1 {
					.text_26 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_27 {
						overflow-wrap: break-word;
						color: rgba(80, 186, 174, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin: 2rpx 96rpx 0 0;
					}
				}
			}
			.image-wrapper_3 {
				box-shadow: 0px 2px 10px 0px rgba(0, 0, 0, 0.12);
				background-color: rgba(255, 255, 255, 0.91);
				border-radius: 5px;
				height: 96rpx;
				width: 96rpx;
				position: absolute;
				left: 654rpx;
				top: 290rpx;
				padding: 16rpx 16rpx 16rpx 16rpx;
				.label_1 {
					width: 64rpx;
					height: 64rpx;
				}
			}
			.thumbnail_11 {
				position: absolute;
				left: 44rpx;
				top: 562rpx;
				width: 40rpx;
				height: 40rpx;
			}
		}
	}
}

.pop_content {
	background: #fff;
	border-top-left-radius: 10px;
	border-top-right-radius: 10px;
	.box_1 {
		background-color: transparent;
		padding: 56rpx 32rpx 40rpx 30rpx;
		.block_3 {
			position: relative;
			width: 680rpx;
			margin-left: 8rpx;
			padding: 10rpx 0 4rpx 24rpx;
			.box_2 {
				background-color: rgba(165, 229, 215, 1);
				border-radius: 5px;
				width: 80rpx;
				height: 20rpx;
				margin-top: 14rpx;
			}
			.thumbnail_1 {
				width: 26rpx;
				height: 26rpx;
				// border: 1px solid rgba(153, 153, 153, 1);
				margin-bottom: 8rpx;
			}
			.text_1 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(69, 69, 69, 1);
				font-size: 34rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: left;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.box_3 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 50%;
			width: 36rpx;
			height: 36rpx;
			// border: 1px solid rgba(220, 220, 220, 1);
			margin: 26rpx 0 26rpx 0;
		}
		.block_4 {
			margin: 86rpx 4rpx 0 0;

			.image-text_1 {
				width: 414rpx;
				margin-left: 32rpx;
				.box_4 {
					border-radius: 3px;
					background-image: url(/static/quanchengpeizhen2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_1 {
					margin-top: 6rpx;
					.text_2 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-right: 200rpx;
					}
					.text_3 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 8rpx;
					}
				}
			}
			.image-text_2 {
				margin: 10rpx 0 4rpx 154rpx;
				.thumbnail_2 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_2 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_1 {
			width: 616rpx;
			height: 4rpx;
			margin: 32rpx 6rpx 0 66rpx;
		}
		.block_5 {
			margin: 40rpx 4rpx 0 0;
			.thumbnail_3 {
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(77, 187, 177, 1);
				margin: 26rpx 0 26rpx 0;
			}
			.image-text_3 {
				width: 316rpx;
				margin-left: 32rpx;
				.box_5 {
					border-radius: 3px;
					background-image: url(/static/daibanmaiyao2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_3 {
					margin: 2rpx 0 8rpx 0;
					.text_4 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 0 102rpx 0 2rpx;
					}
					.text_5 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 4rpx;
					}
				}
			}
			.image-text_4 {
				margin: 4rpx 0 10rpx 252rpx;
				.thumbnail_4 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_4 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_2 {
			width: 616rpx;
			height: 4rpx;
			margin: 26rpx 6rpx 0 66rpx;
			background: #e6e6e6;
		}
		.block_6 {
			margin: 38rpx 4rpx 0 0;
			.box_6 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin: 22rpx 0 30rpx 0;
			}
			.image-text_5 {
				width: 484rpx;
				margin-left: 32rpx;
				.group_1 {
					border-radius: 3px;
					background-image: url(/static/daibanwenzhen2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_5 {
					margin: 4rpx 0 6rpx 0;
					.text_6 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 0 270rpx 0 2rpx;
					}
					.text_7 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 4rpx;
					}
				}
			}
			.image-text_6 {
				margin: 6rpx 0 8rpx 84rpx;
				.thumbnail_5 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_6 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_3 {
			width: 616rpx;
			height: 4rpx;
			margin: 32rpx 6rpx 0 66rpx;
		}
		.block_7 {
			margin: 30rpx 4rpx 0 0;
			.block_8 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin: 26rpx 0 26rpx 0;
			}
			.image-text_7 {
				width: 520rpx;
				margin-left: 32rpx;
				.block_9 {
					border-radius: 3px;
					background-image: url(/static/qusongjieguo@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_7 {
					margin-top: 8rpx;
					.text_8 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 0 306rpx 0 2rpx;
					}
					.text_9 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 6rpx;
					}
				}
			}
			.image-text_8 {
				margin: 12rpx 0 2rpx 48rpx;
				.thumbnail_6 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_8 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_4 {
			width: 616rpx;
			height: 4rpx;
			margin: 34rpx 6rpx 0 66rpx;
		}
		.block_10 {
			margin: 34rpx 4rpx 0 0;
			.group_2 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin: 26rpx 0 26rpx 0;
			}
			.image-text_9 {
				width: 316rpx;
				margin-left: 32rpx;
				.section_2 {
					border-radius: 3px;
					background-image: url(/static/xunxiangfuwu2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_9 {
					margin: 4rpx 0 4rpx 0;
					.text_10 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 0 102rpx 0 2rpx;
					}
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 6rpx;
					}
				}
			}
			.image-text_10 {
				margin: 8rpx 0 6rpx 235rpx;
				.thumbnail_7 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_10 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_5 {
			width: 268rpx;
			height: 10rpx;
			align-self: center;
			margin-top: 90rpx;
		}
	}
}
</style>
