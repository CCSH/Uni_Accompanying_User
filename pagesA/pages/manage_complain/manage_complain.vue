<template>
	<view class="page flex-col">
		<view class="group_3 flex-col justify-between">
			<view class="section_2 flex-col">
				<view class="section_3 flex-row">
					<view class="image-text_1 flex-col">
						<image class="image_4" referrerpolicy="no-referrer" src="/static/img_zanwu@2x.png" />
						<text class="text-group_1">暂无数据~</text>
					</view>
				</view>
	
			</view>
			<view class="section_5 flex-col">
				<view class="text-wrapper_4 flex-col" @click="gotoComplain">
					<text class="text_7">去反馈</text>
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
    gotoComplain() {
      uni.navigateTo({
        url: '/pagesA/pages/add_complain/add_complain',
      })
    },
  },
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	// height: 1624rpx;
	overflow: hidden;
	.group_3 {
		background-color: rgba(246, 246, 246, 1);
    height: 100vh;
		.section_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.group_4 {
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
					.text_6 {
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
			.group_5 {
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
		.section_2 {
			padding: 112rpx 0 40rpx 186rpx;
			.section_3 {
				margin-right: 210rpx;
				.image-text_1 {
					.image_4 {
						width: 354rpx;
						height: 274rpx;
					}
					.text-group_1 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 38rpx 102rpx 0 126rpx;
					}
				}
			}
			.section_4 {
				margin: 690rpx 0 0 468rpx;
				.block_2 {
					box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
					border-radius: 7px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/03766a02da75402d81887e7eead1d595_mergeImage.png);
					width: 96rpx;
					height: 96rpx;
				}
			}
		}
		.section_5 {
			background-color: rgba(254, 255, 255, 1);
			margin-top: -2rpx;
			padding: 16rpx 28rpx 18rpx 32rpx;
			.text-wrapper_4 {
				background-color: rgba(80, 186, 174, 1);
				border-radius: 19px;
				padding: 18rpx 302rpx 18rpx 304rpx;
				.text_7 {
					overflow-wrap: break-word;
					color: rgba(254, 254, 254, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.image_5 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 40rpx;
			}
		}
	}
}
</style>
