<template>
	<view class="page flex-col">
		<view class="box_2 flex-col justify-between">
			<view class="group_1 flex-col">
				<view class="box_5 flex-col">
					<view class="group_2 flex-row">
						<text class="text_6">赵洪莉</text>
						<text class="text_7">193****1095</text>
						<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/bianji@2x.png" @click="gotoEdit" />
					</view>
					<view class="text-wrapper_3 flex-row">
						<text class="text_8">鸿博家园一期B区6号楼3单元801</text>
					</view>
				</view>
			</view>
			<view class="group_3 flex-col">
				<view class="text-wrapper_4 flex-col" @click="gotoAdd">
					<text class="text_9">添加地址</text>
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
		}
	},
	methods: {
		gotoEdit() {
			uni.navigateTo({ url: '/pagesA/pages/add_address/add_address?edit=true' })
		},
		gotoAdd() {
			uni.navigateTo({ url: '/pagesA/pages/add_address/add_address' })
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	overflow: hidden;
	.box_2 {
		background-color: rgba(246, 246, 246, 1);
		height: 100vh;
		.block_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.box_3 {
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
			.box_4 {
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
		.group_1 {
			padding: 24rpx 0 40rpx 20rpx;
			.box_5 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 10px;
				margin-right: 20rpx;
				padding: 36rpx 32rpx 34rpx 32rpx;
				.group_2 {
					.text_6 {
						overflow-wrap: break-word;
						color: rgba(69, 69, 69, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_7 {
						overflow-wrap: break-word;
						color: rgba(69, 69, 69, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-left: 36rpx;
					}
					.thumbnail_6 {
						width: 28rpx;
						height: 28rpx;
						margin: 34rpx 0 0 332rpx;
					}
				}
				.text-wrapper_3 {
					margin: 4rpx 298rpx 0 0;
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
			.box_6 {
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/92fc375a33f3469c86b51283f1840b03_mergeImage.png);
				width: 96rpx;
				height: 96rpx;
				margin: 960rpx 0 0 634rpx;
			}
		}
		.group_3 {
			background-color: rgba(254, 255, 255, 1);
			margin-top: -2rpx;
			padding: 16rpx 28rpx 18rpx 32rpx;
			.text-wrapper_4 {
				background-color: rgba(80, 186, 174, 1);
				border-radius: 19px;
				padding: 18rpx 288rpx 18rpx 290rpx;
				.text_9 {
					overflow-wrap: break-word;
					color: rgba(254, 254, 254, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.image_4 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 40rpx;
			}
		}
	}
}
</style>
