<template>
	<view class="page flex-col">
		<view class="section_1 flex-col">
			<view class="group_2 flex-col">
				<view class="group_5 flex-row">
					<view class="image-text_1 flex-row justify-between">
						<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/sousuo@2x.png" />
						<input placeholder="请输入医院名称" class="text-group_1" />
					</view>
				</view>
			</view>
			<view class="block_1 flex-col" @click="gotoDetail">
				<view class="image-text_2 flex-row justify-between">
					<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
					<text class="text-group_2">成都市新津区龙蟠路509路</text>
				</view>
				<view class="image-text_3 flex-row justify-between">
					<image class="thumbnail_8" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
					<text class="text-group_3">成都市武侯区一环路西一段132号</text>
				</view>
				<view class="image-text_4 flex-row justify-between">
					<image class="thumbnail_9" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
					<text class="text-group_4">成都市二环路北四段4号</text>
				</view>
				<view class="image-text_5 flex-row justify-between">
					<image class="thumbnail_10" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
					<text class="text-group_5">成都市二环路北二段82号</text>
				</view>
				<view class="image-text_6 flex-row justify-between">
					<image class="thumbnail_11" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
					<text class="text-group_6">四川省成都市蓉都大道天回路270号</text>
				</view>
				<view class="image-text_7 flex-row justify-between">
					<image class="thumbnail_12" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
					<text class="text-group_7">成都市高新西区尚锦路253号</text>
				</view>
				<view class="image-text_8 flex-row justify-between">
					<view class="box_3 flex-col"></view>
					<view class="box_4 flex-col">
						<text class="text-group_8">四川省骨科医院（天府院区）</text>
						<view class="text-wrapper_3 flex-col">
							<text class="text_6">三甲医院</text>
						</view>
					</view>
				</view>
				<view class="image-text_9 flex-row justify-between">
					<view class="group_6 flex-col"></view>
					<view class="group_7 flex-col">
						<text class="text-group_9">四川省骨科医院</text>
						<view class="text-wrapper_4 flex-col">
							<text class="text_7">三甲医院</text>
						</view>
					</view>
				</view>
				<view class="image-text_10 flex-row justify-between">
					<view class="box_5 flex-col"></view>
					<view class="box_6 flex-col">
						<text class="text-group_10">成都416医院</text>
						<view class="text-wrapper_5 flex-col">
							<text class="text_8">三甲医院</text>
						</view>
					</view>
				</view>
				<view class="image-text_11 flex-row justify-between">
					<view class="section_2 flex-col"></view>
					<view class="section_3 flex-col">
						<text class="text-group_11">成都大学附属医院</text>
						<view class="text-wrapper_6 flex-col">
							<text class="text_9">三甲医院</text>
						</view>
					</view>
				</view>
				<view class="image-text_12 flex-row justify-between">
					<view class="box_7 flex-col"></view>
					<view class="box_8 flex-col">
						<text class="text-group_12">成都军区总医院</text>
						<view class="text-wrapper_7 flex-col">
							<text class="text_10">三甲医院</text>
						</view>
					</view>
				</view>
				<view class="image-text_13 flex-row justify-between">
					<view class="section_4 flex-col"></view>
					<view class="section_5 flex-col">
						<text class="text-group_13">成都上锦南府医院</text>
						<view class="text-wrapper_8 flex-col">
							<text class="text_11">三甲医院</text>
						</view>
					</view>
				</view>
			</view>
			<view class="image-wrapper_1 flex-col">
				<image class="image_4" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng5a55bce0e61824e6b35e82f487c8fc2828194ab82d71f586b93de2f8b36bc031" />
			</view>
		</view>
	</view>
</template>
<script>
export default {
	data() {
		return {
			constants: {},
		}
	},
	methods: {
		gotoDetail() {
			uni.navigateTo({ url: '/pagesA/pages/service_detail/service_detail' })
			// uni.navigateTo({ url: '/pagesA/pages/hospital_detail/hospital_detail' })
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	overflow: hidden;
	.section_1 {
		background-color: rgba(246, 246, 246, 1);
		position: relative;
		padding-bottom: 26rpx;
		.group_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 18rpx 30rpx;
			.group_3 {
				margin: 0 18rpx 0 12rpx;
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
			.group_4 {
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
					margin-left: 244rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 136rpx;
				}
			}
			.group_5 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 17px;
				margin: 24rpx 20rpx 0 0;
				padding: 16rpx 462rpx 16rpx 20rpx;
				.image-text_1 {
					width: 208rpx;
					.thumbnail_6 {
						width: 30rpx;
						height: 30rpx;
						margin-top: 4rpx;
					}
					.text-group_1 {
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
		.block_1 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 5px;
			position: relative;
			margin: 26rpx 10rpx 0 12rpx;
			padding: 134rpx 140rpx 126rpx 182rpx;
			.image-text_2 {
				width: 312rpx;
				margin-right: 94rpx;
				.thumbnail_7 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_2 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_3 {
				width: 380rpx;
				margin: 170rpx 26rpx 0 0;
				.thumbnail_8 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_3 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_4 {
				width: 284rpx;
				margin: 168rpx 122rpx 0 0;
				.thumbnail_9 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_4 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_5 {
				width: 298rpx;
				margin: 170rpx 108rpx 0 0;
				.thumbnail_10 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_5 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_6 {
				width: 406rpx;
				margin-top: 168rpx;
				.thumbnail_11 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_6 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_7 {
				width: 336rpx;
				margin: 170rpx 70rpx 0 0;
				.thumbnail_12 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_7 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_8 {
				position: absolute;
				left: 16rpx;
				top: 24rpx;
				width: 528rpx;
				height: 146rpx;
				.box_3 {
					border-radius: 10px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/f274d2d85eef43d0b48fb5eafe1bbc55_mergeImage.png);
					width: 144rpx;
					height: 144rpx;
					margin-top: 2rpx;
				}
				.box_4 {
					margin-bottom: 54rpx;
					.text-group_8 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text-wrapper_3 {
						background-color: rgba(82, 183, 175, 1);
						border-radius: 3px;
						margin: 16rpx 252rpx 0 0;
						padding: 0 10rpx 2rpx 6rpx;
						.text_6 {
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
			.image-text_9 {
				position: absolute;
				left: 16rpx;
				top: 228rpx;
				width: 360rpx;
				height: 146rpx;
				.group_6 {
					border-radius: 10px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/c4e73a428938490ebdb77c08a0ecde08_mergeImage.png);
					width: 144rpx;
					height: 144rpx;
					margin-top: 2rpx;
				}
				.group_7 {
					margin-bottom: 54rpx;
					.text-group_9 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text-wrapper_4 {
						background-color: rgba(82, 183, 175, 1);
						border-radius: 3px;
						margin: 16rpx 84rpx 0 0;
						padding: 0 10rpx 2rpx 6rpx;
						.text_7 {
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
			.image-text_10 {
				position: absolute;
				left: 16rpx;
				top: 430rpx;
				width: 322rpx;
				height: 146rpx;
				.box_5 {
					border-radius: 10px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/5369cc80baf946ef95e60837c5ebeffe_mergeImage.png);
					width: 144rpx;
					height: 144rpx;
					margin-top: 2rpx;
				}
				.box_6 {
					margin-bottom: 54rpx;
					.text-group_10 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text-wrapper_5 {
						background-color: rgba(82, 183, 175, 1);
						border-radius: 3px;
						margin: 16rpx 46rpx 0 0;
						padding: 0 10rpx 2rpx 6rpx;
						.text_8 {
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
			.image-text_11 {
				position: absolute;
				left: 16rpx;
				top: 634rpx;
				width: 388rpx;
				height: 146rpx;
				.section_2 {
					border-radius: 10px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/d08a631d26be407fac33ff6d2e03972b_mergeImage.png);
					width: 144rpx;
					height: 144rpx;
					margin-top: 2rpx;
				}
				.section_3 {
					margin-bottom: 54rpx;
					.text-group_11 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text-wrapper_6 {
						background-color: rgba(82, 183, 175, 1);
						border-radius: 3px;
						margin: 16rpx 112rpx 0 0;
						padding: 0 10rpx 2rpx 6rpx;
						.text_9 {
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
			.image-text_12 {
				position: absolute;
				left: 16rpx;
				top: 836rpx;
				width: 360rpx;
				height: 146rpx;
				.box_7 {
					border-radius: 10px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/a372cc8ffb43411887bcbb4cd8cc8177_mergeImage.png);
					width: 144rpx;
					height: 144rpx;
					margin-top: 2rpx;
				}
				.box_8 {
					margin-bottom: 54rpx;
					.text-group_12 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text-wrapper_7 {
						background-color: rgba(82, 183, 175, 1);
						border-radius: 3px;
						margin: 16rpx 84rpx 0 0;
						padding: 0 10rpx 2rpx 6rpx;
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
			.image-text_13 {
				position: absolute;
				left: 16rpx;
				top: 1040rpx;
				width: 388rpx;
				height: 146rpx;
				.section_4 {
					border-radius: 10px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/62a28fad446c4bc28a3d4309170db448_mergeImage.png);
					width: 144rpx;
					height: 144rpx;
					margin-top: 2rpx;
				}
				.section_5 {
					margin-bottom: 54rpx;
					.text-group_13 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text-wrapper_8 {
						background-color: rgba(82, 183, 175, 1);
						border-radius: 3px;
						margin: 16rpx 112rpx 0 0;
						padding: 0 10rpx 2rpx 6rpx;
						.text_11 {
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
		.image-wrapper_1 {
			position: absolute;
			left: 0;
			top: 1598rpx;
			width: 750rpx;
			height: 28rpx;
			.image_4 {
				width: 268rpx;
				height: 10rpx;
				margin: -2rpx 240rpx 20rpx 242rpx;
			}
		}
	}
}
</style>
