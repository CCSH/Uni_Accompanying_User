<template>
	<view class="page flex-col">
		<view class="box_1 flex-col">
			<view class="box_2 flex-col">
				<view class="list_2 flex-col">
					<view class="list-items_1 flex-row justify-between" v-for="(item, index) in loopData0" :key="index">
						<view class="text-group_3 flex-col">
							<text class="text_4">{{ item.lanhutext0 }}</text>
							<text class="text_5">{{ item.lanhutext1 }}</text>
						</view>
						<view class="text-group_4 flex-col">
							<view class="text-wrapper_2">
								<text class="text_6">{{ item.lanhutext2 }}</text>
								<text class="text_7">{{ item.lanhutext3 }}</text>
							</view>
							<text class="text_8">{{ item.lanhutext4 }}</text>
						</view>
						<!-- <image class="thumbnail_4" referrerpolicy="no-referrer" :src="item.lanhuimage0" /> -->
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
			loopData0: [
				{
					lanhutext0: '陪诊优惠券',
					lanhutext1: '有效期至2024.06.06',
					lanhutext2: '￥',
					lanhutext3: '100',
					lanhutext4: '满800可用',
					lanhuimage0: 'https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/6f3e2ccb09dd4453903835211ee91f47_mergeImage.png',
				},
				{
					lanhutext0: '陪诊优惠券',
					lanhutext1: '有效期至2024.06.06',
					lanhutext2: '￥',
					lanhutext3: '10',
					lanhutext4: '满100可用',
					lanhuimage0: 'https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/9b77c00aeed8421b9b713b93b043b062_mergeImage.png',
				},
			],
			constants: {},
		}
	},
	methods: {},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	// height: 1624rpx;
	overflow: hidden;
	.box_1 {
		background-color: rgba(246, 246, 246, 1);
		// height: 1624rpx;
		.group_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 22rpx 40rpx;
			.group_3 {
				margin: 0 18rpx 0 2rpx;
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
					.text_9 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_10 {
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
				.thumbnail_5 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_6 {
					width: 30rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 10rpx;
				}
				.image_4 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.group_4 {
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
					margin-left: 260rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 154rpx;
				}
			}
		}
		.box_2 {
			padding: 24rpx 22rpx 20rpx 22rpx;
			.list_2 {
				height: 376rpx;
				.list-items_1 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 5px;
					border: 1px solid rgba(80, 186, 174, 1);
					margin-bottom: 24rpx;
					padding: 38rpx 26rpx 36rpx 24rpx;
					.text-group_3 {
						margin-top: 6rpx;
						.text_4 {
							overflow-wrap: break-word;
							color: rgba(51, 51, 51, 1);
							font-size: 34rpx;
							font-family: PingFangSC-Semibold;
							font-weight: 600;
							text-align: left;
							white-space: nowrap;
							line-height: 48rpx;
							margin-right: 54rpx;
						}
						.text_5 {
							overflow-wrap: break-word;
							color: rgba(102, 102, 102, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
							margin-top: 10rpx;
						}
					}
					.text-group_4 {
						margin-left: 246rpx;
						.text-wrapper_2 {
							width: 100rpx;
							height: 60rpx;
							overflow-wrap: break-word;
							font-size: 0;
							font-family: PingFangSC-Semibold;
							font-weight: 600;
							text-align: right;
							line-height: 40rpx;
							align-self: center;
							.text_6 {
								width: 100rpx;
								height: 60rpx;
								overflow-wrap: break-word;
								color: rgba(80, 186, 174, 1);
								font-size: 28rpx;
								font-family: PingFangSC-Semibold;
								font-weight: 600;
								text-align: left;
								line-height: 40rpx;
							}
							.text_7 {
								width: 100rpx;
								height: 60rpx;
								overflow-wrap: break-word;
								color: rgba(80, 186, 174, 1);
								font-size: 44rpx;
								font-family: PingFangSC-Semibold;
								font-weight: 600;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text_8 {
							width: 116rpx;
							overflow-wrap: break-word;
							color: rgba(80, 186, 174, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: right;
							white-space: nowrap;
							line-height: 34rpx;
							margin-top: 4rpx;
						}
					}
					.thumbnail_4 {
						width: 32rpx;
						height: 32rpx;
						margin: 32rpx 0 34rpx 34rpx;
					}
				}
			}
			.image_5 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 1020rpx;
			}
		}
	}
}
</style>
