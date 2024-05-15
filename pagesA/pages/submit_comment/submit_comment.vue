<template>
	<view class="page flex-col">
		<view class="box_1 flex-col">
			<view class="section_5 flex-col">
				<view class="image-text_10 flex-row justify-between">
					<image class="thumbnail_9" referrerpolicy="no-referrer" src="/static/pingjia@2x.png" />
					<text class="text-group_1">客观真实的评价能帮助用户做决策</text>
				</view>
			</view>
			<view class="box_4 flex-col">
				<view class="block_1 flex-col">
					<view class="group_12 flex-row">
						<view class="group_2 flex-col"></view>
						<text class="text_4">陪诊员：李华</text>
						<image class="thumbnail_5" referrerpolicy="no-referrer" src="/static/sep_line.png" />
						<text class="text_5">男</text>
						<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/sep_line.png" />
						<text class="text_6">电话：19339208023</text>
					</view>
					<view class="group_13 flex-row">
						<view class="image-text_12 flex-row justify-between">
							<text class="text_7">服务描述</text>
						</view>
						<image class="thumbnail_12" referrerpolicy="no-referrer" src="/static/wuxing@2x.png" />
						<view class="image-text_13 flex-row justify-between">
							<text class="text_8">非常好</text>
						</view>
					</view>
				</view>
				<view class="group_14 flex-row justify-between">
					<view class="text-wrapper_2 flex-col">
						<text class="text_9">整体评价</text>
					</view>
					<view class="text-wrapper_3 flex-col">
						<text class="text_10">沟通情况</text>
					</view>
					<view class="text-wrapper_4 flex-col">
						<text class="text_11">卫生服务</text>
					</view>
					<view class="text-wrapper_5 flex-col">
						<text class="text_12">服务态度</text>
					</view>
				</view>
				<textarea class="text_13" placeholder="展开说说对陪诊员的想法吧…" />
				<view class="group_15 flex-row justify-between">
					<view class="text-wrapper_6 flex-col" @click="back">
						<text class="text_14">取消</text>
					</view>
					<view class="text-wrapper_7 flex-col" @click="handleSubmit">
						<text class="text_15">发布</text>
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
		}
	},
	methods: {
    back(){
      uni.navigateBack()
    },
    handleSubmit(){
      uni.showToast({
        title: '评论成功',
        icon: 'none',
        duration:1000,
      })
      setTimeout(() => {
        uni.reLaunch({ url: '/pages/home/home' })
      }, 1000);
    }
  },
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	height: 1624rpx;
	overflow: hidden;
	.box_1 {
		background-color: rgba(246, 246, 246, 1);
		.box_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.group_10 {
				margin: 0 18rpx 0 2rpx;
				.text-wrapper_10 {
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
					.text_20 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_21 {
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
				.thumbnail_18 {
					width: 34rpx;
					height: 22rpx;
					margin: 4rpx 0 8rpx 438rpx;
				}
				.thumbnail_19 {
					width: 30rpx;
					height: 22rpx;
					margin: 2rpx 0 10rpx 10rpx;
				}
				.image_10 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.group_11 {
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
					margin-left: 278rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 170rpx;
				}
			}
		}
		.section_5 {
			padding: 18rpx 20rpx 22rpx 20rpx;
			.image-text_10 {
				width: 390rpx;
				align-self: center;
				.thumbnail_9 {
					width: 24rpx;
					height: 22rpx;
					margin: 6rpx 0 6rpx 0;
				}
				.text-group_1 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: right;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-wrapper_1 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 12px;
				margin-top: 20rpx;
				padding: 64rpx 270rpx 50rpx 270rpx;
				.image-text_11 {
					.image-wrapper_2 {
						background: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/f1bfb0bd59ef473993b95a95a1232827_mergeImage.png) 100% no-repeat;
						background-size: 100% 100%;
						margin: 0 60rpx 0 62rpx;
						padding: 32rpx 6rpx 0 38rpx;
						.thumbnail_10 {
							width: 4rpx;
							height: 14rpx;
						}
					}
					.text-group_2 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 34rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 48rpx;
						margin-top: 8rpx;
					}
				}
			}
		}
		.box_4 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 20px 20px 0px 0px;
			margin-top: -2rpx;
			padding: 20rpx 18rpx 18rpx 20rpx;
			.block_1 {
				background-color: rgba(246, 246, 246, 1);
				border-radius: 9px;
				padding: 24rpx 30rpx 36rpx 28rpx;
				.group_12 {
					.group_2 {
						border-radius: 50%;
						background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/281af144fc8e4cf383315c114d7a889e_mergeImage.png);
						width: 60rpx;
						height: 60rpx;
					}
					.text_4 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 34rpx;
						margin: 14rpx 0 0 12rpx;
					}
					.thumbnail_5 {
						width: 2rpx;
						height: 26rpx;
						margin: 20rpx 0 14rpx 52rpx;
					}
					.text_5 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 34rpx;
						margin: 14rpx 0 0 46rpx;
					}
					.thumbnail_6 {
						width: 2rpx;
						height: 26rpx;
						margin: 20rpx 0 14rpx 44rpx;
					}
					.text_6 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 34rpx;
						margin: 14rpx 0 0 42rpx;
					}
				}
				.group_13 {
					margin: 22rpx 178rpx 0 0;
					.image-text_12 {
						// width: 144rpx;
						margin-bottom: 2rpx;
						.text_7 {
							overflow-wrap: break-word;
							color: rgba(51, 51, 51, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: right;
							white-space: nowrap;
							line-height: 34rpx;
						}
						.thumbnail_11 {
							width: 36rpx;
							height: 34rpx;
						}
					}
					.thumbnail_12 {
						width: 278rpx;
						height: 34rpx;
						margin: 0 0 2rpx 24rpx;
					}
					.thumbnail_13 {
						width: 36rpx;
						height: 34rpx;
						margin: 0 0 2rpx 22rpx;
					}
					.thumbnail_14 {
						width: 36rpx;
						height: 34rpx;
						margin: 0 0 2rpx 24rpx;
					}
					.image-text_13 {
						width: 130rpx;
						margin-left: 24rpx;
						.thumbnail_15 {
							width: 36rpx;
							height: 34rpx;
							margin-bottom: 2rpx;
						}
						.text_8 {
							overflow-wrap: break-word;
							color: rgba(247, 90, 35, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: right;
							white-space: nowrap;
							line-height: 34rpx;
							margin-top: 2rpx;
						}
					}
				}
			}
			.group_14 {
				width: 672rpx;
				align-self: center;
				margin-top: 48rpx;
				.text-wrapper_2 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 14px;
					border: 1px dashed rgba(200, 200, 200, 1);
					padding: 8rpx 22rpx 10rpx 22rpx;
					.text_9 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_3 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 14px;
					border: 1px dashed rgba(200, 200, 200, 1);
					padding: 8rpx 22rpx 10rpx 22rpx;
					.text_10 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_4 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 14px;
					border: 1px dashed rgba(200, 200, 200, 1);
					padding: 8rpx 22rpx 10rpx 22rpx;
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.text-wrapper_5 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 14px;
					border: 1px dashed rgba(200, 200, 200, 1);
					padding: 8rpx 22rpx 10rpx 22rpx;
					.text_12 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
			}
			.text_13 {
				overflow-wrap: break-word;
				color: rgba(153, 153, 153, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				white-space: nowrap;
				line-height: 40rpx;
				margin: 30rpx 20rpx 0 20rpx;
			}
			.group_15 {
				width: 364rpx;
				margin: 60rpx 20rpx 0 328rpx;
				.text-wrapper_6 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 19px;
					border: 1px solid rgba(153, 153, 153, 1);
					padding: 16rpx 56rpx 16rpx 56rpx;
					.text_14 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
				.text-wrapper_7 {
					background-color: rgba(80, 186, 174, 1);
					border-radius: 19px;
					border: 1px solid rgba(83, 184, 176, 1);
					padding: 16rpx 56rpx 16rpx 56rpx;
					.text_15 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
			}
			.image_11 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 40rpx;
			}
		}
	}
}
</style>
