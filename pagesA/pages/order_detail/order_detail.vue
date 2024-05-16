<template>
	<view class="page flex-col">
		<view class="box_4 flex-col">
			<view class="box_15 flex-col">
				<view class="block_2 flex-row">
					<view class="image-text_2 flex-col">
						<image class="label_1" referrerpolicy="no-referrer" src="/static/yiwancheng@2x.png" />
						<text class="text-group_1">填写订单</text>
					</view>
					<image class="image_4" referrerpolicy="no-referrer" src="/static/point_line.png" />
					<view class="box_16 flex-col">
						<view class="text-wrapper_3 flex-col">
							<text class="text_6">2</text>
						</view>
						<text class="text_7">在线支付</text>
					</view>
					<image class="image_5" referrerpolicy="no-referrer" src="/static/point_line.png" />
					<view class="box_17 flex-col">
						<view class="text-wrapper_4 flex-col">
							<text class="text_8">3</text>
						</view>
						<text class="text_9">服务中</text>
					</view>
					<image class="image_6" referrerpolicy="no-referrer" src="/static/point_line.png" />
					<view class="box_18 flex-col">
						<view class="text-wrapper_5 flex-col">
							<text class="text_10">4</text>
						</view>
						<text class="text_11">服务完成</text>
					</view>
				</view>
				<view class="block_3 flex-row">
					<view class="text-group_3 flex-col">
						<text class="text_12">订单待支付</text>
						<view class="text-wrapper_6">
							<text class="text_13">请在</text>
							<text class="text_14">00:14:16</text>
							<text class="text_15">&nbsp;内完成支付，超时订单自动取消。</text>
						</view>
					</view>
				</view>
			</view>
			<view class="block_4 flex-col">
				<view class="block_7 flex-row">
					<view class="section_6 flex-col"></view>
					<text class="text_16">预约信息</text>
				</view>
				<view class="text-wrapper_13 flex-row justify-between">
					<text class="paragraph_1">
						<text style="display: block">就诊医院</text>

						<br />
						<text style="display: block">就诊科室</text>

						<br />
						<text style="display: block">就诊时间</text>

						<br />
						<text style="display: block">就诊人</text>

						<br />
						<text style="display: block">联系电话</text>

						<br />
						<text style="display: block">身份证号</text>

						<br />
						<text style="display: block">就诊人关系</text>
					</text>
					<text class="paragraph_2">
						<text style="display: block">四川省骨科语言</text>

						<br />
						<text style="display: block">足裸2科</text>

						<br />
						<text style="display: block">2024-05-28&nbsp;21:35</text>

						<br />
						<text style="display: block">赵洪莉</text>

						<br />
						<text style="display: block">193****95</text>

						<br />
						<text style="display: block">1306********024</text>

						<br />
						<text style="display: block">本人</text>
					</text>
				</view>
			</view>
			<view class="block_5 flex-col">
				<view class="box_19 flex-row">
					<view class="box_9 flex-col"></view>
					<text class="text_17">订单信息</text>
				</view>
				<view class="box_20 flex-row justify-between">
					<text class="paragraph_3">
						<text style="display: block">服务项目</text>

						<br />
						<text style="display: block">陪诊时长</text>

						<br />
						<text style="display: block">订单号</text>

						<br />
						<text style="display: block">下单时间</text>

						<br />
						<text style="display: block">订单金额</text>

						<br />
						<text style="display: block">优惠券</text>
					</text>
					<view class="text-wrapper_8">
						<text class="paragraph_4">
							<text style="display: block">全程陪诊</text>

							<br />
							<text style="display: block">半天陪诊</text>

							<br />
							<text style="display: block">2825058EW2S</text>

							<br />
							<text style="display: block">2024-05-28&nbsp;19:00:00</text>

							<br />
						</text>
						<text class="paragraph_5">
							<text style="display: block">￥268.00</text>

							<br />
						</text>
						<text class="text_18" style="display: block">有0张可使用</text>
					</view>
				</view>
				<!-- <view class="box_11 flex-col"></view> -->
			</view>
			<view class="block_6 flex-col">
				<view class="group_1 flex-row">
					<text class="text_19">共计</text>
					<view class="text-wrapper_9">
						<text class="text_20">￥</text>
						<text class="text_21">268</text>
						<text class="text_22">.00</text>
					</view>
					<view class="text-wrapper_10 flex-col" @click="handleCancel">
						<text class="text_23">取消订单</text>
					</view>
					<view class="text-wrapper_11 flex-col" @click="handlePlay">
						<text class="text_24">立即支付</text>
					</view>
				</view>
				<view class="image-wrapper_2 flex-row">
					<image class="image_9" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng5a55bce0e61824e6b35e82f487c8fc2828194ab82d71f586b93de2f8b36bc031" />
				</view>
			</view>
		</view>
		<!-- 悬浮 -->
		<drag-button  :isDock="true" :existTabBar="true"></drag-button>
		<!-- 弹窗 -->
		<uni-popup ref="popup_cancel" type="dialog" class="dialog" background-color="#fff" borderRadius="10rpx   10rpx   10rpx   10rpx">
			<view class="group_3 flex-col">
				<view class="box_7 flex-row justify-between">
					<view class="block_2 flex-col"></view>
					<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_cancel.close()" />
					<text class="text_4">取消订单</text>
				</view>
				<view class="box_8 flex-row">
					<view class="block_3 flex-col"></view>
					<text class="text_5">取消</text>
					<text class="text_8">取消订单后，您将无法查看该订单，确认继续删除该订单吗？</text>
				</view>
				<view class="box_9 flex-row justify-between">
					<view class="text-wrapper_3 flex-col" @click="$refs.popup_cancel.close()">
						<text class="text_9">取消</text>
					</view>
					<view class="text-wrapper_4 flex-col" @click="$refs.popup_cancel.close()">
						<text class="text_10">确定</text>
					</view>
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
			constants: {},
		}
	},
	methods: {
		handlePlay() {
			uni.showToast({
				title: '支付成功',
				icon: 'success',
				mask: true,
				duration: 1000,
			})
			setTimeout(() => {
				uni.navigateBack()
			}, 1000)
		},
		handleCancel() {
			this.$refs.popup_cancel.open()
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	overflow: hidden;
	.box_4 {
		background-color: rgba(246, 246, 246, 1);
		.box_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.box_13 {
				margin: 0 18rpx 0 2rpx;
				.text-wrapper_12 {
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
					.text_25 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_26 {
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
				.thumbnail_6 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_7 {
					width: 30rpx;
					height: 22rpx;
					margin: 2rpx 0 10rpx 10rpx;
				}
				.image_8 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.box_14 {
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
		.box_15 {
			padding: 22rpx 20rpx 26rpx 20rpx;
			.block_2 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				padding: 30rpx 28rpx 30rpx 26rpx;
				.image-text_2 {
					.label_1 {
						width: 52rpx;
						height: 52rpx;
						align-self: center;
					}
					.text-group_1 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-top: 12rpx;
					}
				}
				.image_4 {
					width: 42rpx;
					height: 2rpx;
					margin: 28rpx 0 74rpx 16rpx;
				}
				.box_16 {
					margin-left: 20rpx;
					.text-wrapper_3 {
						background-color: rgba(81, 187, 164, 1);
						border-radius: 50%;
						align-self: center;
						width: 52rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
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
					.text_7 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
						margin-top: 12rpx;
					}
				}
				.image_5 {
					width: 54rpx;
					height: 2rpx;
					margin: 28rpx 0 74rpx 16rpx;
				}
				.box_17 {
					margin-left: 8rpx;
					.text-wrapper_4 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin: 0 14rpx 0 18rpx;
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
					.text_9 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
						margin-top: 12rpx;
					}
				}
				.image_6 {
					width: 54rpx;
					height: 2rpx;
					margin: 28rpx 0 74rpx 16rpx;
				}
				.box_18 {
					margin-left: 10rpx;
					.text-wrapper_5 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin: 0 26rpx 0 34rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_10 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
						margin-top: 12rpx;
					}
				}
			}
			.block_3 {
				background: url(/static/order_bg.png) 100% no-repeat;
				background-size: 100% 100%;
				margin-top: 24rpx;
				padding: 32rpx 78rpx 32rpx 32rpx;
				.text-group_3 {
					.text_12 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 34rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 48rpx;
						margin-right: 430rpx;
					}
					.text-wrapper_6 {
						width: 600rpx;
						height: 40rpx;
						overflow-wrap: break-word;
						font-size: 0;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-top: 12rpx;
						.text_13 {
							overflow-wrap: break-word;
							color: rgba(255, 255, 255, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
						.text_14 {
							overflow-wrap: break-word;
							color: rgba(226, 239, 137, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
						.text_15 {
							overflow-wrap: break-word;
							color: rgba(255, 255, 255, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
				}
			}
		}
		.block_4 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			align-self: center;
			margin-top: -2rpx;
			width: 710rpx;
			padding: 42rpx 28rpx 16rpx 30rpx;
			.block_7 {
				position: relative;
				margin: 0 514rpx 0 2rpx;
				padding: 24rpx 22rpx 4rpx 34rpx;
				.section_6 {
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
					color: rgba(51, 51, 51, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
			.text-wrapper_13 {
				width: 652rpx;
				margin-top: 36rpx;
				.paragraph_1 {
					width: 140rpx;
					height: 552rpx;
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 78rpx;
				}
				.paragraph_2 {
					width: 248rpx;
					height: 552rpx;
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: right;
					line-height: 78rpx;
				}
			}
		}
		.block_5 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			align-self: center;
			margin-top: 20rpx;
			width: 710rpx;
			position: relative;
			padding: 30rpx 28rpx 10rpx 30rpx;
			.box_19 {
				position: relative;
				margin: 0 514rpx 0 2rpx;
				padding: 24rpx 22rpx 4rpx 34rpx;
				.box_9 {
					background-color: rgba(165, 229, 215, 1);
					border-radius: 5px;
					width: 80rpx;
					height: 20rpx;
				}
				.text_17 {
					position: absolute;
					left: 0;
					top: 0;
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
			.box_20 {
				width: 652rpx;
				margin-top: 38rpx;
				.paragraph_3 {
					width: 112rpx;
					// height: 474rpx;
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 78rpx;
				}
				.text-wrapper_8 {
					width: 288rpx;
					// height: 474rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: center;
					line-height: 78rpx;
					.paragraph_4 {
						width: 288rpx;
						// height: 474rpx;
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						line-height: 78rpx;
					}
					.paragraph_5 {
						width: 288rpx;
						// height: 474rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 174, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						line-height: 78rpx;
					}
					.text_18 {
						width: 288rpx;
						// height: 474rpx;
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						line-height: 78rpx;
					}
				}
			}
			.box_11 {
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/02f53be8ceed4fa1a9d929e997ed7674_mergeImage.png);
				position: absolute;
				left: 634rpx;
				top: -10rpx;
				width: 96rpx;
				height: 96rpx;
			}
		}
		.block_6 {
			box-shadow: 0px -4px 10px 0px rgba(0, 0, 0, 0.04);
			background-color: rgba(254, 255, 255, 1);
			margin-top: 24rpx;
			padding: 20rpx 20rpx 18rpx 40rpx;
			.group_1 {
				.text_19 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
					margin-top: 10rpx;
				}
				.text-wrapper_9 {
					width: 142rpx;
					height: 62rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
					margin: 8rpx 0 6rpx 6rpx;
					.text_20 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 62rpx;
					}
					.text_21 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 40rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 62rpx;
					}
					.text_22 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 62rpx;
					}
				}
				.text-wrapper_10 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 19px;
					border: 1px solid rgba(230, 230, 230, 1);
					margin-left: 86rpx;
					padding: 20rpx 46rpx 18rpx 48rpx;
					.text_23 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_11 {
					background-color: rgba(81, 187, 164, 1);
					border-radius: 19px;
					margin-left: 12rpx;
					padding: 22rpx 48rpx 20rpx 50rpx;
					.text_24 {
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
				margin: 16rpx 220rpx 0 202rpx;
				.image_9 {
					width: 268rpx;
					height: 10rpx;
				}
			}
		}
	}
}

.dialog {
	background: #fff;
	.group_3 {
		background: #fff;
		// background: url(https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngcb35ff0cd823ed383a1e9d36753420090c769b076fc9a52a536095391a4ea5f8) 100% no-repeat;
		// background-size: 100% 100%;
		padding: 40rpx 38rpx 58rpx 36rpx;
		.box_7 {
			position: relative;
			width: 514rpx;
			margin: 0 4rpx 0 2rpx;
			padding: 6rpx 0 10rpx 52rpx;
			.block_2 {
				background-color: rgba(167, 227, 219, 1);
				border-radius: 4px;
				width: 62rpx;
				height: 16rpx;
				margin: 14rpx 0 2rpx 0;
			}
			.thumbnail_6 {
				width: 32rpx;
				height: 32rpx;
			}
			.text_4 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 34rpx;
				letter-spacing: 2.5999999046325684px;
				font-family: PingFangSC-Medium;
				font-weight: 500;
				text-align: right;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.box_8 {
			position: relative;
			margin: 56rpx 16rpx 0 0;
			padding: 8rpx 450rpx 44rpx 0;
			.block_3 {
				background-color: rgba(255, 255, 255, 1);
				width: 54rpx;
				height: 28rpx;
			}
			.text_5 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(70, 70, 70, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: right;
				white-space: nowrap;
				line-height: 40rpx;
			}
			.text_8 {
				position: absolute;
				left: 0;
				top: 0;
				width: 504rpx;
				height: 80rpx;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				line-height: 40rpx;
			}
		}
		.box_9 {
			width: 520rpx;
			margin-top: 60rpx;
			.text-wrapper_3 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 19px;
				border: 1px solid rgba(230, 230, 230, 1);
				padding: 20rpx 94rpx 18rpx 94rpx;
				.text_9 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.text-wrapper_4 {
				background-color: rgba(240, 98, 96, 1);
				border-radius: 19px;
				padding: 22rpx 96rpx 20rpx 96rpx;
				.text_10 {
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
	}
}
</style>
