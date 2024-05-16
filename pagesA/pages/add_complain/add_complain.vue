<template>
	<view class="page flex-col">
		<view class="group_5 flex-col">
			<view class="block_1 flex-col">
				<view class="section_1 flex-col"></view>
				<text class="text_6">投诉原因</text>
				<view class="grid_1 flex-row">
					<view :class="(list.indexOf(0) != -1 ? 'text_h' : '') + ' text-wrapper_3 flex-col'" @click="handleClick(0)">
						<text class="text_7">回复不及时</text>
					</view>
					<view :class="(list.indexOf(1) != -1 ? 'text_h' : '') + ' text-wrapper_4 flex-col'" @click="handleClick(1)">
						<text class="text_8">服务态度差</text>
					</view>
					<view :class="(list.indexOf(2) != -1 ? 'text_h' : '') + ' text-wrapper_5 flex-col'" @click="handleClick(2)">
						<text class="text_9">工作效率低</text>
					</view>
					<view :class="(list.indexOf(3) != -1 ? 'text_h' : '') + ' text-wrapper_6 flex-col'" @click="handleClick(3)">
						<text class="text_10">会面迟到</text>
					</view>
				</view>
				<text class="text_11">具体原因（非必填）</text>
				<view class="text-wrapper_7 flex-col">
					<textarea class="text_12" placeholder="请描述您要投诉的具体原因" />
				</view>
				<!-- <view class="section_2 flex-row">
					<view class="image-text_1 flex-col">
						<image class="thumbnail_6" referrerpolicy="no-referrer" src="https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/e1dd465a43c74162a384d1ed805418ec_mergeImage.png" />
						<view class="text-group_1">
							<text class="paragraph_1">
								添加图片
								<br />
							</text>
							<text class="text_13">（最多9张）</text>
						</view>
					</view>
				</view> -->
				<text class="text_14">在线投诉</text>
			</view>
			<view class="block_2 flex-col">
				<view class="text-wrapper_8 flex-col" @click="back">
					<text class="text_15">提交</text>
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
			list: [],
		}
	},
	methods: {
		back() {
			uni.showToast({
				title: '提交成功',
				icon: 'none',
				duration: 1000,
			})
			setTimeout(() => {
				uni.navigateBack()
			}, 1000)
		},
		handleClick(val) {
			if (this.list.indexOf(val) != -1) {
				this.list.splice(this.list.indexOf(val), 1)
			} else {
				this.list.push(val)
			}
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
	.group_5 {
		background-color: rgba(246, 246, 246, 1);
		height: 1624rpx;
		.group_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 22rpx 40rpx;
			.group_6 {
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
					margin: 4rpx 0 8rpx 10rpx;
				}
				.image_3 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.group_7 {
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
					margin-left: 244rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 136rpx;
				}
			}
		}
		.block_1 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 10px;
			position: relative;
			width: 710rpx;
			align-self: center;
			margin-top: 24rpx;
			padding: 64rpx 22rpx 60rpx 28rpx;
			.section_1 {
				background-color: rgba(165, 229, 215, 1);
				border-radius: 5px;
				width: 80rpx;
				height: 20rpx;
				margin: 0 546rpx 0 34rpx;
			}
			.text_6 {
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				white-space: nowrap;
				line-height: 40rpx;
				margin: 38rpx 548rpx 0 0;
			}
			.grid_1 {
				width: 418rpx;
				height: 152rpx;
				flex-wrap: wrap;
				margin: 40rpx 242rpx 0 0;
				.text_h {
					border: 1px solid #51bba4;
				}
				.text-wrapper_3 {
					background-color: rgba(247, 247, 247, 1);
					border-radius: 15px;
					height: 60rpx;
					width: 192rpx;
					margin: 0 34rpx 32rpx 0;
					padding: 14rpx 36rpx 12rpx 36rpx;
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
				.text-wrapper_4 {
					background-color: rgba(247, 247, 247, 1);
					border-radius: 15px;
					height: 60rpx;
					margin-bottom: 32rpx;
					width: 192rpx;
					padding: 14rpx 36rpx 12rpx 36rpx;
					.text_8 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_5 {
					background-color: rgba(247, 247, 247, 1);
					border-radius: 15px;
					height: 60rpx;
					width: 192rpx;
					margin: 0 34rpx 32rpx 0;
					padding: 14rpx 36rpx 12rpx 36rpx;
					.text_9 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_6 {
					background-color: rgba(247, 247, 247, 1);
					border-radius: 15px;
					height: 60rpx;
					margin-bottom: 32rpx;
					width: 192rpx;
					padding: 14rpx 48rpx 12rpx 48rpx;
					.text_10 {
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
			.text_11 {
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				white-space: nowrap;
				line-height: 40rpx;
				margin: 52rpx 408rpx 0 0;
			}
			.text-wrapper_7 {
				background-color: rgba(247, 247, 247, 1);
				border-radius: 8px;
				margin-top: 20rpx;
				padding: 30rpx 30rpx 30rpx 30rpx;
				.text_12 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.section_2 {
				border-radius: 6px;
				border: 1px solid rgba(230, 230, 230, 1);
				margin: 26rpx 520rpx 0 0;
				padding: 6rpx 14rpx 8rpx 18rpx;
				.image-text_1 {
					.thumbnail_6 {
						width: 34rpx;
						height: 32rpx;
						margin: 0 38rpx 0 32rpx;
					}
					.text-group_1 {
						width: 104rpx;
						height: 40rpx;
						overflow-wrap: break-word;
						font-size: 0;
						font-weight: normal;
						text-align: right;
						line-height: 20rpx;
						margin-top: 10rpx;
						.paragraph_1 {
							width: 104rpx;
							height: 40rpx;
							overflow-wrap: break-word;
							color: rgba(153, 153, 153, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							line-height: 20rpx;
						}
						.text_13 {
							width: 104rpx;
							height: 40rpx;
							overflow-wrap: break-word;
							color: rgba(153, 153, 153, 1);
							font-size: 18rpx;
							font-weight: normal;
							text-align: left;
							line-height: 20rpx;
						}
					}
				}
			}
			.text_14 {
				position: absolute;
				left: 28rpx;
				top: 40rpx;
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
		.block_2 {
			padding: 24rpx 0 20rpx 32rpx;
			.text-wrapper_8 {
				background-color: rgba(81, 187, 164, 1);
				border-radius: 19px;
				margin-right: 28rpx;
				padding: 18rpx 316rpx 18rpx 318rpx;
				.text_15 {
					overflow-wrap: break-word;
					color: rgba(254, 254, 254, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.box_1 {
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/4ba01bee725341598c0e1a4d6f1a1da7_mergeImage.png);
				width: 96rpx;
				height: 96rpx;
				margin: 158rpx 0 0 622rpx;
			}
			.image_4 {
				width: 268rpx;
				height: 10rpx;
				margin: 170rpx 240rpx 0 210rpx;
			}
		}
	}
}
</style>
