<template>
	<view class="page flex-col">
		<view class="box_1 flex-col">
			<view class="section_2 flex-col">
				<view class="text-wrapper_22 flex-row">
					<view class="tab">
						<text :class="index == 0 ? 'text_h text_4' : 'text_4'" @click="index = 0">全部</text>
						<view v-show="index == 0" class="group_1 flex-col"></view>
					</view>
					<view class="tab">
						<text :class="index == 1 ? 'text_h text_5' : 'text_5'" @click="index = 1">待支付</text>
						<view v-show="index == 1" class="group_1 flex-col"></view>
					</view>
					<view class="tab">
						<text :class="index == 2 ? 'text_h text_6' : 'text_6'" @click="index = 2">进行中</text>
						<view v-show="index == 2" class="group_1 flex-col"></view>
					</view>
					<view class="tab">
						<text :class="index == 3 ? 'text_h text_7' : 'text_7'" @click="index = 3">待评价</text>
						<view v-show="index == 3" class="group_1 flex-col"></view>
					</view>
				</view>
			</view>
			<view class="box_6 flex-col" @click="gotoDetail">
				<view class="block_6 flex-row justify-between">
					<view class="image-text_14 flex-row justify-between">
						<view class="group_4 flex-col"></view>
						<text class="text-group_2">订单号&nbsp;28250528EW2S</text>
					</view>
					<view class="text-wrapper_5 flex-col">
						<text class="text_10">待支付</text>
					</view>
				</view>
				<image class="image_5" referrerpolicy="no-referrer" src="" />
				<view class="section_5 flex-row">
					<view class="box_7 flex-col"></view>
					<text class="text_11">半天陪诊</text>
					<text class="text_12">￥&nbsp;268.00</text>
				</view>
				<view class="text-wrapper_23 flex-row justify-between">
					<text class="paragraph_1">
						<text style="display: block">就诊人：</text>
						<br />
						<text style="display: block">就诊医院：</text>
						<br />
						<text style="display: block">就诊时间：</text>
					</text>
					<text class="paragraph_2">
						<text style="display: block">赵洪莉</text>
						<br />
						<text style="display: block">四川省骨科医院</text>
						<br />
						<text style="display: block">2024-05-28&nbsp;21:35</text>
					</text>
				</view>
				<view class="block_7 flex-row justify-between">
					<text class="text_13">共计</text>
					<view class="text-wrapper_7">
						<text class="text_14">￥</text>
						<text class="text_15">268</text>
						<text class="text_16">.00</text>
					</view>
				</view>
				<image class="image_6" referrerpolicy="no-referrer" src="" />
				<view class="block_8 flex-row">
					<view class="image-text_15 flex-row justify-between">
						<image class="thumbnail_13" referrerpolicy="no-referrer" src="/static/shijian-10@2x.png" />
						<view class="text-group_3">
							<text class="text_17">剩余时间:</text>
							<text class="text_18">00:13</text>
						</view>
					</view>
					<view class="text-wrapper_8 flex-col">
						<text class="text_19" @click="handleCancel">取消订单</text>
					</view>
					<view class="text-wrapper_9 flex-col" @click="handlePlay">
						<text class="text_20">立即支付</text>
					</view>
				</view>
			</view>
			<view class="box_6 flex-col" @click="gotoDetail">
				<view class="block_6 flex-row justify-between">
					<view class="image-text_14 flex-row justify-between">
						<view class="group_4 flex-col"></view>
						<text class="text-group_2">订单号&nbsp;28250528EW2S</text>
					</view>
					<view class="text-wrapper_5 flex-col text-wrapper_5-c">
						<text class="text_10">待评价</text>
					</view>
				</view>
				<image class="image_5" referrerpolicy="no-referrer" src="" />
				<view class="section_5 flex-row">
					<view class="box_7 flex-col"></view>
					<text class="text_11">半天陪诊</text>
					<text class="text_12">￥&nbsp;268.00</text>
				</view>
				<view class="text-wrapper_23 flex-row justify-between">
					<text class="paragraph_1">
						<text style="display: block">就诊人：</text>
						<br />
						<text style="display: block">就诊医院：</text>
						<br />
						<text style="display: block">就诊时间：</text>
					</text>
					<text class="paragraph_2">
						<text style="display: block">赵洪莉</text>
						<br />
						<text style="display: block">四川省骨科医院</text>
						<br />
						<text style="display: block">2024-05-28&nbsp;21:35</text>
					</text>
				</view>
				<view class="block_7 flex-row justify-between">
					<text class="text_13">共计</text>
					<view class="text-wrapper_7">
						<text class="text_14">￥</text>
						<text class="text_15">268</text>
						<text class="text_16">.00</text>
					</view>
				</view>
				<image class="image_6" referrerpolicy="no-referrer" src="" />
				<view class="block_8 flex-row justify-end">
					<!-- <view class="image-text_15 flex-row flex-end"> -->
					<!-- <image class="thumbnail_13" referrerpolicy="no-referrer" src="/static/shijian-10@2x.png" />
						<view class="text-group_3">
							<text class="text_17">剩余时间:</text>
							<text class="text_18">00:13</text>
						</view> -->
					<!-- </view> -->
					<!-- <view class="text-wrapper_8 flex-col"> -->
					<!-- <text class="text_19" @click="handleCancel">取消订单</text> -->
					<!-- </view> -->
					<view class="text-wrapper_9 flex-col text-wrapper_9-c" @click="gotoComment">
						<text class="text_20">评价</text>
					</view>
				</view>
			</view>
		</view>
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
export default {
	data() {
		return {
			index: 0,
			constants: {},
		}
	},
	methods: {
		isLogin() {
			let userInfo = uni.getStorageSync('userInfo')
			if (!userInfo) {
				uni.showToast({
					title: '用户未登录',
					icon: 'none',
					duration: 1000,
				})
				setTimeout(() => {
					uni.navigateTo({ url: '/pagesA/pages/login/login' })
				}, 1000)
				return false
			}
			return true
		},
		handlePlay() {
			uni.showToast({
				title: '支付成功',
				icon: 'success',
				mask: true,
				duration: 1000,
			})
		},
		handleCancel() {
			this.$refs.popup_cancel.open()
		},
		gotoDetail() {
			uni.navigateTo({ url: '/pagesA/pages/order_detail/order_detail' })
		},
		gotoComment(){
			uni.navigateTo({ url: '/pagesA/pages/submit_comment/submit_comment' })
		}
	},
	onShow() {
		if (!this.isLogin()) {
			return
		}
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
		.section_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 22rpx 40rpx;
			.group_11 {
				margin: 0 18rpx 0 2rpx;
				.text-wrapper_21 {
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
					.text_32 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_33 {
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
				.thumbnail_11 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_12 {
					width: 30rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 10rpx;
				}
				.image_14 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.group_12 {
				margin-top: 30rpx;
				.thumbnail_3 {
					width: 24rpx;
					height: 40rpx;
					margin: 2rpx 0 18rpx 0;
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
					margin-left: 278rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 170rpx;
				}
			}
		}
		.section_2 {
			background-color: rgba(246, 246, 246, 1);
			align-self: center;
			margin-top: 28rpx;
			width: 710rpx;
			padding: 10rpx 32rpx 14rpx 40rpx;
			.text-wrapper_22 {
				justify-content: space-between;
				.text_h {
					color: rgba(80, 186, 174, 1) !important;
					font-weight: 600 !important;
					font-size: 34rpx !important;
				}
				.text_4 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: right;
					white-space: nowrap;
					line-height: 40rpx;
					margin: 4rpx 0 0 0;
				}
				.text_5 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: right;
					white-space: nowrap;
					line-height: 40rpx;
					margin: 4rpx 0 0 0;
				}
				.text_6 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: right;
					white-space: nowrap;
					line-height: 40rpx;
					margin: 4rpx 0 0 0;
				}
				.text_7 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: right;
					white-space: nowrap;
					line-height: 40rpx;
					margin: 4rpx 0 0 0;
				}
			}
			.tab {
				display: flex;
				flex-direction: column;
				align-items: center;
			}
			// .block_5 {
			// 	margin: 20rpx 0 0 22rpx;
			.group_1 {
				margin-top: 22rpx;
				// margin-bottom: 26rpx;
				background-color: rgba(80, 186, 174, 1);
				border-radius: 2px;
				width: 24rpx;
				height: 6rpx;
			}
			// }
		}
		.box_6 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			width: 710rpx;
			align-self: center;
			margin-top: 12rpx;
			padding: 42rpx 28rpx 38rpx 0;
			margin-bottom: 12rpx;
			.block_6 {
				width: 680rpx;
				margin-right: 2rpx;
				.image-text_14 {
					width: 338rpx;
					.group_4 {
						background-color: rgba(81, 187, 164, 1);
						border-radius: 0px 100px 100px 0px;
						width: 14rpx;
						height: 12rpx;
						margin: 12rpx 0 16rpx 0;
					}
					.text-group_2 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
				.text-wrapper_5 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 10px;
					border: 1px solid rgba(255, 148, 148, 1);
					padding: 0 12rpx 0 16rpx;
					.text_10 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
				.text-wrapper_5-c {
					border: 1px solid #50baae;
					.text_10 {
						color: #50baae;
					}
				}
			}
			.image_5 {
				width: 650rpx;
				height: 2rpx;
				margin: 42rpx 2rpx 0 30rpx;
				background: #e6e6e6;
			}
			.section_5 {
				background-color: rgba(246, 246, 246, 1);
				border-radius: 6px;
				margin: 32rpx 4rpx 0 30rpx;
				padding: 24rpx 14rpx 24rpx 28rpx;
				.box_7 {
					background-color: rgba(81, 187, 164, 1);
					border-radius: 50%;
					width: 8rpx;
					height: 8rpx;
					margin: 16rpx 0 16rpx 0;
				}
				.text_11 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 8rpx;
				}
				.text_12 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: center;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 348rpx;
				}
			}
			.text-wrapper_23 {
				width: 388rpx;
				margin: 20rpx 266rpx 0 28rpx;
				.paragraph_1 {
					width: 140rpx;
					height: 186rpx;
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
				}
				.paragraph_2 {
					width: 248rpx;
					height: 186rpx;
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
				}
			}
			.block_7 {
				width: 208rpx;
				margin: 20rpx 0 0 474rpx;
				.text_13 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
					margin-top: 4rpx;
				}
				.text-wrapper_7 {
					width: 142rpx;
					height: 62rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
					margin-bottom: 4rpx;
					.text_14 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 62rpx;
					}
					.text_15 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 40rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 62rpx;
					}
					.text_16 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 62rpx;
					}
				}
			}
			.image_6 {
				width: 650rpx;
				height: 2rpx;
				margin: 20rpx 2rpx 0 30rpx;
				background: #e6e6e6;
			}
			.block_8 {
				margin: 20rpx 2rpx 0 30rpx;
				.image-text_15 {
					width: 206rpx;
					margin: 20rpx 0 22rpx 0;
					.thumbnail_13 {
						width: 28rpx;
						height: 28rpx;
						margin: 4rpx 0 2rpx 0;
					}
					.text-group_3 {
						width: 170rpx;
						height: 34rpx;
						overflow-wrap: break-word;
						font-size: 0;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						.text_17 {
							overflow-wrap: break-word;
							color: rgba(102, 102, 102, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
						}
						.text_18 {
							overflow-wrap: break-word;
							color: rgba(255, 81, 81, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
						}
					}
				}
				.text-wrapper_8 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 19px;
					border: 1px solid rgba(230, 230, 230, 1);
					margin-left: 44rpx;
					padding: 20rpx 46rpx 18rpx 48rpx;
					.text_19 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_9 {
					background-color: rgba(81, 187, 164, 1);
					border-radius: 19px;
					margin-left: 12rpx;
					padding: 22rpx 48rpx 20rpx 50rpx;
					.text_20 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_9-c {
					background-color: #fff;
					border: 1px solid rgba(81, 187, 164, 1) !important;
					.text_20 {
						color: rgba(81, 187, 164, 1);
					}
				}
			}
		}
		.box_8 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			position: relative;
			width: 710rpx;
			align-self: center;
			margin-top: 24rpx;
			padding: 42rpx 28rpx 0 0;
			.block_9 {
				width: 680rpx;
				margin-right: 2rpx;
				.image-text_16 {
					width: 334rpx;
					.group_5 {
						background-color: rgba(81, 187, 164, 1);
						border-radius: 0px 100px 100px 0px;
						width: 14rpx;
						height: 12rpx;
						margin: 12rpx 0 16rpx 0;
					}
					.text-group_4 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
				.text-wrapper_10 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 10px;
					border: 1px solid rgba(220, 220, 220, 1);
					padding: 0 12rpx 0 16rpx;
					.text_21 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
			}
			.image_7 {
				width: 650rpx;
				height: 2rpx;
				margin: 42rpx 2rpx 0 30rpx;
			}
			.box_10 {
				background-color: rgba(246, 246, 246, 1);
				border-radius: 6px;
				margin: 32rpx 4rpx 0 30rpx;
				padding: 24rpx 14rpx 24rpx 28rpx;
				.box_11 {
					background-color: rgba(81, 187, 164, 1);
					border-radius: 50%;
					width: 8rpx;
					height: 8rpx;
					margin: 16rpx 0 16rpx 0;
				}
				.text_22 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 8rpx;
				}
				.text_23 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: center;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 354rpx;
				}
			}
			.text-wrapper_24 {
				width: 382rpx;
				margin: 20rpx 272rpx 0 28rpx;
				.paragraph_3 {
					width: 140rpx;
					height: 186rpx;
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
				}
				.paragraph_4 {
					width: 242rpx;
					height: 186rpx;
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
				}
			}
			.block_10 {
				width: 208rpx;
				margin: 20rpx 0 0 474rpx;
				.text_24 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
					margin-top: 4rpx;
				}
				.text-wrapper_12 {
					width: 142rpx;
					height: 62rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: left;
					line-height: 62rpx;
					margin-bottom: 4rpx;
					.text_25 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 62rpx;
					}
					.text_26 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 40rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 62rpx;
					}
					.text_27 {
						overflow-wrap: break-word;
						color: rgba(255, 81, 81, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 62rpx;
					}
				}
			}
			.image_8 {
				width: 650rpx;
				height: 2rpx;
				margin: 20rpx 2rpx 0 30rpx;
			}
			.block_11 {
				width: 382rpx;
				margin: 18rpx 12rpx 0 288rpx;
				.box_14 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 19px;
					width: 178rpx;
					height: 14rpx;
					border: 1px solid rgba(230, 230, 230, 1);
				}
				.box_15 {
					background-color: rgba(81, 187, 164, 1);
					border-radius: 19px;
					width: 174rpx;
					height: 12rpx;
					margin-top: 2rpx;
				}
			}
			.box_16 {
				box-shadow: 0px -4px 10px 0px rgba(0, 0, 0, 0.04);
				background-color: rgba(254, 255, 255, 1);
				position: absolute;
				left: -20rpx;
				top: 432rpx;
				width: 750rpx;
				height: 160rpx;
				padding: 26rpx 70rpx 18rpx 70rpx;
				.list_5 {
					width: 610rpx;
					height: 84rpx;
					justify-content: space-between;
					.image-text_17 {
						margin-right: 140rpx;
						.label_2 {
							width: 44rpx;
							height: 44rpx;
							align-self: center;
						}
						.text-group_5 {
							overflow-wrap: break-word;
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
							margin-top: 6rpx;
						}
					}
				}
				.image_15 {
					width: 268rpx;
					height: 10rpx;
					align-self: center;
					margin-top: 22rpx;
				}
			}
			.box_17 {
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/339ae691f8a34e64b82a1fc04cbfe0a0_mergeImage.png);
				position: absolute;
				left: 634rpx;
				top: 242rpx;
				width: 96rpx;
				height: 96rpx;
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
