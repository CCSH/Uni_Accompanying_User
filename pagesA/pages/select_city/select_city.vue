<template>
	<view class="page flex-col">
		<view class="group_1 flex-col">
			<view class="section_2 flex-col">
				<view class="text-wrapper_4 flex-row">
					<view class="image-text_2 flex-row justify-between">
						<image class="thumbnail_10" referrerpolicy="no-referrer" src="/static/sousuo@2x.png" mode="aspectFit" />
						<input class="text_7" placeholder="请输入城市名称"/>
					</view>
				</view>
			</view>
			<view class="group_6 flex-col">
				<view class="section_7 flex-row justify-between">
					<text class="text_8">成都市</text>
					<view class="image-text_3 flex-row justify-between" @click="handleLocation">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_1">重新定位</text>
					</view>
				</view>
				<view class="section_11 flex-row">
					<view class="box_1 flex-col"></view>
					<text class="text_9">选择已开通城市</text>
				</view>
				<view class="section_12 flex-row justify-between">
					<view class="group_7 flex-col">
						<view :class="cityIndex == 0 ? 'box_2 flex-row' : 'box_2 flex-row box_2_h'" @click="handleCity(0)">
							<view class="section_10 flex-col"></view>
							<text class="text_10">四川省</text>
						</view>
						<view :class="cityIndex == 1 ? 'box_2 flex-row' : 'box_2 flex-row box_2_h'" @click="handleCity(1)">
							<view class="section_10 flex-col"></view>
							<text class="text_10">黑龙江省</text>
						</view>
					</view>
					<view class="block_3">
						<view v-for="(item, i) in cityData" :key="i" class="flex-row justify-between text-wrapper_2" @click="handleList(i)">
							<text :class="index == i ? 'content' : 'content content_h'">{{ item }}</text>
							<img v-if="index == i" class="check" src="/static/xuanze@2x.png" alt="" />
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
export default {
	data() {
		return {
			constants: {},
			cityIndex: 0,
			index: 0,
			cityData: ['泸州市', '泸州市2', '泸州市2', '泸州市3', '泸州市4', '泸州市5', '泸州市6'],
		}
	},
	methods: {
		handleCity(val) {
			this.cityIndex = val
		},
		handleList(val) {
			this.index = val
			uni.navigateBack()
		},
		handleLocation() {
			uni.showToast({
				title: '定位成功',
				icon: 'none',
				duration: 1000,
			})
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	height: 1624rpx;
	overflow: hidden;
	.group_1 {
		background-color: rgba(246, 246, 246, 1);
		height: 1624rpx;
		.section_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 18rpx 30rpx;
			.group_4 {
				margin: 0 18rpx 0 12rpx;
				.text-wrapper_5 {
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
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_12 {
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
				.thumbnail_8 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_9 {
					width: 30rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 10rpx;
				}
				.image_5 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.group_5 {
				margin: 30rpx 0 0 10rpx;
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
					margin-left: 192rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 86rpx;
				}
			}
			.text-wrapper_4 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 17px;
				margin: 24rpx 20rpx 0 0;
				padding: 16rpx 462rpx 16rpx 20rpx;
				.image-text_2 {
					width: 208rpx;
					.thumbnail_10 {
						width: 30rpx;
						height: 30rpx;
						margin-top: 4rpx;
            margin-right: 10rpx;
					}
					.text_7 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
			}
		}
		.group_6 {
			padding-bottom: 4rpx;
			.section_7 {
				background-color: rgba(255, 255, 255, 1);
				width: 750rpx;
				padding: 28rpx 30rpx 30rpx 30rpx;
				.text_8 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-top: 2rpx;
				}
				.image-text_3 {
					width: 150rpx;
					margin-bottom: 2rpx;
					.thumbnail_7 {
						width: 22rpx;
						height: 28rpx;
						margin: 6rpx 0 6rpx 0;
					}
					.text-group_1 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
			}
			.section_11 {
				position: relative;
				margin: 48rpx 482rpx 0 30rpx;
				padding: 24rpx 124rpx 4rpx 34rpx;
				.box_1 {
					background-color: rgba(165, 229, 215, 1);
					width: 80rpx;
					height: 20rpx;
				}
				.text_9 {
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
			.section_12 {
				width: 750rpx;
				margin-top: 30rpx;
				.group_7 {
					margin-bottom: 148rpx;
					align-items: center;
					.box_2_h {
						background-color: #f6f6f6 !important;
						.section_10 {
							background-color: transparent !important;
						}
					}
					.box_2 {
						background-color: rgba(255, 255, 255, 1);
						width: 302rpx;
						text-align: left;
						// padding-right: 186rpx;
						.section_10 {
							background-color: rgba(82, 183, 175, 1);
							width: 4rpx;
							height: 106rpx;
						}
						.text_10 {
							margin-left: 32rpx;
							overflow-wrap: break-word;
							color: rgba(51, 51, 51, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
							margin-top: 32rpx;
						}
					}
					.paragraph_1 {
						width: 84rpx;
						height: 880rpx;
						overflow-wrap: break-word;
						color: rgba(137, 137, 137, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 110rpx;
						margin: 0 186rpx 0 32rpx;
					}
				}
				.block_3 {
					background-color: rgba(255, 255, 255, 1);
					position: relative;
					width: 448rpx;
					height: 100%;
					.text-wrapper_2 {
						padding-left: 30rpx;
						padding-right: 38rpx;
						align-items: center;
					}
					.check {
						width: 26rpx;
						height: 20rpx;
					}
					.check_h {
						width: 0 !important;
					}
					.content {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 106rpx;
						height: 106rpx;
					}
					.content_h {
						color: rgba(51, 51, 51, 1) !important;
					}
				}
			}
		}
	}
}
</style>
