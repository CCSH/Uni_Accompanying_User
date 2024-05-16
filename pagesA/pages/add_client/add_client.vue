<template>
	<view class="page flex-col">
		<view class="group_3 flex-col">
			<view class="group_4 flex-col">
				<image class="image_4" referrerpolicy="no-referrer" />
				<image class="image_5" referrerpolicy="no-referrer" />
				<image class="image_6" referrerpolicy="no-referrer" />
				<image class="image_7" referrerpolicy="no-referrer" />
				<text class="paragraph_1">
					<text style="display: block">姓名</text>

					<br />
					<text style="display: block">身份证号</text>

					<br />
					<text style="display: block">联系方式</text>

					<br />
					<text style="display: block">就诊人关系</text>

					<br />
					<text style="display: block" class="flex-col">
						<text>既往病史</text>
						<text class="text_6">（非必填）</text>
					</text>
				</text>
				<view class="text-wrapper_3 justify-between flex-col align-end">
					<!-- <text class="paragraph_2"> -->
					<input placeholder="请输入" />

					<br />
					<input placeholder="请输入" />

					<br />
					<input placeholder="请输入" />

					<br />
					<input placeholder="请输入" />
					<br />
					<input placeholder="请完善就诊人既往病史" />
					<!-- </text> -->
				</view>
			</view>
			<view class="group_5 flex-col">
				<text class="text_8">提示：不满18岁未成年需在家长陪同下就诊。</text>
				<view class="text-wrapper_4 flex-col" @click="back">
					<text class="text_9">保存就诊人</text>
				</view>
				<view v-show="isEdit" class="text-wrapper_5 flex-col" @click="back">
					<text class="text_10">删除</text>
				</view>
				<!-- <view class="box_2 flex-col">s</view> -->
			</view>
		</view>
		<!-- 悬浮 -->
		<drag-button @btnClick="gotoService" :isDock="true" :existTabBar="true"></drag-button>
	</view>
</template>
<script>
import dragButton from '@/components/drag-button/drag-button.vue'

export default {
	components: {
		dragButton,
	},
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
		gotoService() {
			if (!this.isLogin()) {
				return
			}
			uni.navigateTo({ url: '/pagesA/pages/customer_service/customer_service' })
		},
	},
	onLoad(val) {
		console.log(val)
		this.isEdit = val.edit
		if (this.isEdit) {
			uni.setNavigationBarTitle({ title: '编辑就诊人' })
		}
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	overflow: hidden;
	.group_3 {
		background-color: rgba(246, 246, 246, 1);
		.section_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 30rpx 10rpx 22rpx 40rpx;
			.block_1 {
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
			.block_2 {
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
					margin-left: 228rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 118rpx;
				}
			}
		}
		.group_4 {
			height: 592rpx;
			background-color: rgba(255, 255, 255, 1);
			border-radius: 10px;
			position: relative;
			margin: 20rpx 18rpx 0 22rpx;
			// padding: 114rpx 30rpx 36rpx 24rpx;
			.image_4 {
				width: 650rpx;
				height: 2rpx;
				margin-left: 6rpx;
				background: #e6e6e6;
				margin-top: 110rpx;
			}
			.image_5 {
				width: 650rpx;
				height: 2rpx;
				margin: 110rpx 0 0 6rpx;
				background: #e6e6e6;
			}
			.image_6 {
				width: 650rpx;
				height: 2rpx;
				margin: 110rpx 0 0 6rpx;
				background: #e6e6e6;
			}
			.image_7 {
				width: 650rpx;
				height: 2rpx;
				margin: 108rpx 0 0 6rpx;
				background: #e6e6e6;
			}
			.thumbnail_6 {
				width: 10rpx;
				height: 24rpx;
				margin: 42rpx 6rpx 0 640rpx;
			}
			.text_6 {
				overflow-wrap: break-word;
				color: rgba(153, 153, 153, 1);
				font-size: 24rpx;
				font-weight: normal;
				text-align: left;
				white-space: nowrap;
				line-height: 34rpx;
				margin: 6rpx 10rpx 0 0;
				position: relative;
				top: -76rpx;
				left: -7rpx;
			}
			.paragraph_1 {
				position: absolute;
				left: 30rpx;
				top: 0;
				width: 140rpx;
				// height: 560rpx;
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				line-height: 112rpx;
			}
			.text-wrapper_3 {
				position: absolute;
				left: 352rpx;
				top: 34rpx;
				width: 292rpx;
				height: 500rpx;
				overflow-wrap: break-word;
				font-size: 0;
				font-weight: normal;
				text-align: right;
				line-height: 112rpx;
				// .paragraph_2 {
				//   position: relative;
				width: 292rpx;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: right;
				// line-height: 112rpx;
				input {
					height: 40rpx;
					width: 400rpx;
				}
				// }
				.text_7 {
					width: 292rpx;
					height: 560rpx;
					overflow-wrap: break-word;
					color: rgba(210, 210, 210, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 112rpx;
				}
			}
		}
		.group_5 {
			padding: 30rpx 0 40rpx 32rpx;
			.text_8 {
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 24rpx;
				font-weight: normal;
				text-align: left;
				white-space: nowrap;
				line-height: 34rpx;
				margin: 0 218rpx 0 18rpx;
			}
			.text-wrapper_4 {
				background-color: rgba(80, 186, 174, 1);
				border-radius: 19px;
				margin: 40rpx 28rpx 0 0;
				padding: 18rpx 274rpx 18rpx 276rpx;
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
			.text-wrapper_5 {
				background-color: rgba(246, 246, 246, 0.5);
				border-radius: 19px;
				border: 1px solid rgba(240, 98, 96, 0.5);
				margin: 28rpx 28rpx 0 0;
				padding: 16rpx 314rpx 16rpx 316rpx;
				.text_10 {
					overflow-wrap: break-word;
					color: rgba(240, 98, 96, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.box_2 {
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/d77c27e2d33e48518ed8a9737531122f_mergeImage.png);
				width: 96rpx;
				height: 96rpx;
				margin: 258rpx 0 0 622rpx;
			}
		}
	}
}
</style>
