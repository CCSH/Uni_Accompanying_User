<template>
	<view class="page flex-col">
		<view class="section_2 flex-col">
			<view class="box_1 flex-row">
				<image class="image_4" referrerpolicy="no-referrer" />
				<image class="image_5" referrerpolicy="no-referrer" />
				<image class="image_6" referrerpolicy="no-referrer" />
				<view class="paragraph_1 flex-col justify-between align-end">
					<input placeholder="请输入" />
					<input placeholder="请输入" />
					<input placeholder="请输入" />
					<input placeholder="请输入" />
				</view>
				<text class="paragraph_2">
					<text style="display: block">收件人</text>

					<br />
					<text style="display: block">联系方式</text>

					<br />
					<text style="display: block">所在地区</text>

					<br />
					<text style="display: block">详细地址</text>
				</text>
			</view>
			<view class="box_2 flex-col">
				<view class="text-wrapper_3 flex-col" @click="back">
					<text class="text_6">保存地址</text>
				</view>
				<view v-show="isEdit" class="text-wrapper_4 flex-col" @click="back">
					<text class="text_7">删除</text>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
export default {
	data() {
		return {
			isEdit: false,
			constants: {},
		}
	},
	methods: {
		back() {
			uni.navigateBack()
		},
	},
	onLoad(val) {
		this.isEdit = val.edit
		if (this.isEdit) {
			uni.setNavigationBarTitle({ title: '修改地址' })
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
	.section_2 {
		background-color: rgba(246, 246, 246, 1);
		height: 1624rpx;
		.group_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 22rpx 40rpx;
			.group_4 {
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
			.group_5 {
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
		.box_1 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 10px;
			position: relative;
			width: 710rpx;
			align-self: center;
			margin-top: 24rpx;
			justify-content: flex-center;
			padding: 0 30rpx 40rpx 30rpx;
			.image_4 {
				width: 650rpx;
				height: 2rpx;
				margin: 338rpx 0 108rpx 0;
				background: #e6e6e6;
			}
			.image_5 {
				width: 650rpx;
				height: 2rpx;
				margin: 226rpx 0 220rpx -650rpx;
				background: #e6e6e6;
			}
			.image_6 {
				width: 650rpx;
				height: 2rpx;
				margin: 114rpx 0 332rpx -650rpx;
				background: #e6e6e6;
			}
			.paragraph_1 {
        margin-top: 33rpx;
				width: 406rpx;
				height: 387rpx;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: right;
				line-height: 112rpx;
				margin-left: -406rpx;
				input {
					width: 300rpx;
				}
			}
			.paragraph_2 {
				position: absolute;
				left: 30rpx;
				top: 0;
				width: 112rpx;
				height: 448rpx;
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				line-height: 112rpx;
			}
		}
		.box_2 {
			padding: 40rpx 0 200rpx 32rpx;
			.text-wrapper_3 {
				background-color: rgba(80, 186, 174, 1);
				border-radius: 19px;
				margin-right: 28rpx;
				padding: 18rpx 288rpx 18rpx 290rpx;
				.text_6 {
					overflow-wrap: break-word;
					color: rgba(254, 254, 254, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.text-wrapper_4 {
				background-color: rgba(246, 246, 246, 0.5);
				border-radius: 19px;
				border: 1px solid rgba(240, 98, 96, 0.5);
				margin: 30rpx 28rpx 0 0;
				padding: 16rpx 314rpx 16rpx 316rpx;
				.text_7 {
					overflow-wrap: break-word;
					color: rgba(240, 98, 96, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.box_3 {
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/c85581d6601448b898b08762af56d449_mergeImage.png);
				width: 96rpx;
				height: 96rpx;
				margin: 420rpx 0 0 622rpx;
			}
		}
	}
}
</style>
