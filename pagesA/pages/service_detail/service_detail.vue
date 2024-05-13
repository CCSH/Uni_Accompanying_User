<template>
	<view class="page flex-col">
		<view class="box_3 flex-col">
			<view class="block_1 flex-col">
				<!-- <view class="group_2 flex-row">
					<view class="text-wrapper_3">
						<text class="text_3">9:4</text>
						<text class="text_4">1</text>
					</view>
					<image class="thumbnail_1" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngb0bfcfcd7d4aeb38c43b16f73c2c736af22643ff20ae47082ec82556faff4126" />
					<image class="thumbnail_2" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngdc0f3d1e17df748cc02795b49ff804887c5a23cd56d8747c9480e78b8fee1aa1" />
					<image class="image_1" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng22e91f3804b2e0d59fbaaf765f7be7149d2587679e5a419fd8b9079529d97c7e" />
				</view> -->
				<view class="image-wrapper_1 flex-row justify-between">
					<image class="thumbnail_3" referrerpolicy="no-referrer" src="/static/jiantou_zuo@2x.png" @click="goBack" />
					<!-- <image class="image_2" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPnged06853d93958f652e6b4fe35a3a1e732afd37efb1d3a5384a2e4b3242976ffc" /> -->
				</view>
			</view>
			<view class="block_5 flex-col">
				<view class="image-text_1 flex-row justify-between">
					<view class="box_5 flex-col"></view>
					<view class="text-group_1 flex-col">
						<text class="text_7">全程陪诊</text>
						<text class="text_8">全程陪同服务，手续代办服务</text>
					</view>
				</view>
				<view class="text-wrapper_5">
					<text class="text_9">￥</text>
					<text class="text_10">268</text>
					<text class="text_11">.00</text>
					<text class="text_12">&nbsp;起&nbsp;/&nbsp;次</text>
				</view>
				<text class="text_13">【半天陪诊/全天陪诊】仅供白天医院正常工作时间使用，如在非医院正常工作时间需要陪诊服务，您必须选择【夜间急诊】</text>
			</view>
			<view class="block_2 flex-col">
				<view class="block_3 flex-row justify-between">
					<view :class="index == 0 ? 'box_4 flex-col' : 'box_4 flex-col box_4_1'"></view>
					<text :class="index == 0 ? 'text_1 text_5' : 'text_1'" @click="handleClick(0)">服务内容</text>
					<text :class="index == 1 ? 'text_1 text_5' : 'text_1'" @click="handleClick(1)">服务须知</text>
				</view>
				<!-- 内容 -->
				<image v-if="index == 0" src="/static/img_fuwuneirong@2x.png" class="box_1 flex-col" mode="widthFix" />
				<image v-if="index == 1" src="/static/fuwuxuzhi@2x.png" class="box_1 flex-col" mode="widthFix"/>
			</view>
			<view class="block_4 flex-col">
				<view class="text-wrapper_4 flex-col">
					<text class="text_6">立即预约￥268.00</text>
				</view>
				<image class="image_3" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng5a55bce0e61824e6b35e82f487c8fc2828194ab82d71f586b93de2f8b36bc031" />
			</view>
		</view>
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
		goBack() {
			wx.navigateBack({
				delta: 1,
			})
		},
		handleClick(val) {
			this.index = val
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	height: 2628rpx;
	overflow: hidden;
	.box_3 {
		background-color: rgba(246, 246, 246, 1);
		position: relative;
		height: 2628rpx;
		.block_1 {
			background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/f311f1bc95c84829af11c84951b48a5a_mergeImage.png);
			padding: 30rpx 10rpx 386rpx 34rpx;
			.group_2 {
				margin: 0 18rpx 0 8rpx;
				.text-wrapper_3 {
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
					.text_3 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
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
				}
				.thumbnail_1 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_2 {
					width: 30rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 10rpx;
				}
				.image_1 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.image-wrapper_1 {
				width: 706rpx;
				margin-top: 68rpx;
				.thumbnail_3 {
					width: 28rpx;
					height: 28rpx;
					// border: 1px solid rgba(255, 255, 255, 1);
					margin: 14rpx 0 18rpx 0;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
				}
			}
		}
		.block_2 {
			border-radius: 6px;
			background: #fff;
			margin: -126rpx 18rpx 0 20rpx;
			padding: 26rpx 0 0rpx 0;
			.block_3 {
				position: relative;
				width: 278rpx;
				margin: 0 398rpx 0 36rpx;
				padding: 6rpx 0 2rpx 28rpx;
				.box_4 {
					position: absolute;
					background-color: rgba(165, 229, 215, 1);
					border-radius: 5px;
					width: 80rpx;
					height: 20rpx;
					margin-top: 20rpx;
					left: 54rpx;
				}

				.box_4_1 {
					left: 200rpx;
				}
				.text_1 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
					margin-right: 30rpx;
					z-index: 1;
				}
				.text_5 {
					// position: absolute;
					// left: 0;
					// top: 0;
					// overflow-wrap: break-word;

					color: rgba(51, 51, 51, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
				}
			}
			.box_1 {
				width: 712rpx;
				height: 100%;
				margin-top: 16rpx;
			}
		}
		.block_4 {
			padding: 20rpx 28rpx 20rpx 32rpx;
			.text-wrapper_4 {
				background-color: rgba(80, 186, 174, 1);
				border-radius: 19px;
				padding: 16rpx 212rpx 20rpx 246rpx;
				.text_6 {
					overflow-wrap: break-word;
					color: rgba(254, 254, 254, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.image_3 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 40rpx;
			}
		}
		.block_5 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			position: relative;
			left: 20rpx;
			top: -150rpx;
			width: 712rpx;
			height: 376rpx;
			padding: 38rpx 18rpx 40rpx 30rpx;
			.image-text_1 {
				width: 408rpx;
				margin-right: 256rpx;
				.box_5 {
					border-radius: 4px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/9ea56b6500ce4939b29b19f77111b773_mergeImage.png);
					width: 80rpx;
					height: 80rpx;
					margin-bottom: 2rpx;
				}
				.text-group_1 {
					.text_7 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 34rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 48rpx;
						margin-right: 176rpx;
					}
					.text_8 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
			}
			.text-wrapper_5 {
				width: 224rpx;
				height: 60rpx;
				overflow-wrap: break-word;
				font-size: 0;
				font-weight: normal;
				text-align: left;
				line-height: 34rpx;
				margin: 44rpx 440rpx 0 0;
				.text_9 {
					height: 60rpx;
					overflow-wrap: break-word;
					color: rgba(81, 187, 164, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					line-height: 34rpx;
				}
				.text_10 {
					height: 60rpx;
					overflow-wrap: break-word;
					color: rgba(81, 187, 164, 1);
					font-size: 44rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
				.text_11 {
					height: 60rpx;
					overflow-wrap: break-word;
					color: rgba(81, 187, 164, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					line-height: 34rpx;
				}
				.text_12 {
					height: 60rpx;
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					line-height: 34rpx;
				}
			}
			.text_13 {
				width: 664rpx;
				height: 68rpx;
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 24rpx;
				font-weight: normal;
				text-align: left;
				line-height: 34rpx;
				margin-top: 44rpx;
			}
		}
	}
}
</style>
