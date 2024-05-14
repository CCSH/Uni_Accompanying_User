<template>
	<view class="page flex-col">
		<view class="section_1 flex-col">
			<view class="box_6 flex-col">
				<view class="block_5 flex-row" @click="gotoLocation">
					<image class="label_3" referrerpolicy="no-referrer" src="@/static/ditu@2x.png" />
					<text class="text_14">成都市</text>
					<image class="thumbnail_10" referrerpolicy="no-referrer" src="@/static/more_bai@2x.png" />
					<text class="text_15">专业陪诊</text>
				</view>
			</view>
			<!-- banner -->
			<image src="/static/img_banner@2x.png" mode="widthFix" class="box_1 flex-col" />
			<view class="box_3 flex-col">
				<view class="block_1 flex-row justify-between">
					<view class="image-text_2 flex-row justify-between">
						<image class="thumbnail_3" referrerpolicy="no-referrer" src="@/static/1@2x.png" />
						<text class="text-group_2">三甲名院</text>
					</view>
					<view class="image-text_3 flex-row justify-between">
						<image class="thumbnail_4" referrerpolicy="no-referrer" src="@/static/2@2x.png" />
						<text class="text-group_3">权威认证</text>
					</view>
					<view class="image-text_4 flex-row justify-between">
						<image class="thumbnail_5" referrerpolicy="no-referrer" src="@/static/3@2x.png" />
						<text class="text-group_4">服务监管</text>
					</view>
				</view>
			</view>
			<view class="box_4 flex-col">
				<view class="image-wrapper_2 flex-row justify-between">
					<image class="image_6" referrerpolicy="no-referrer" src="@/static/daibanwenzhen@2x(1).png" @click="gotoDetail" />
					<image class="image_7" referrerpolicy="no-referrer" src="@/static/zunxiangfuwu@2x(1).png" @click="gotoDetail" />
				</view>
				<view class="grid_1 flex-row">
					<view class="image-text_5 flex-col" v-for="(item, index) in loopData0" :key="index" @click="gotoDetail">
						<image class="label_2" referrerpolicy="no-referrer" :src="'/static/' + item.lanhuimage0" />
						<text class="text-group_5">{{ item.lanhutext0 }}</text>
					</view>
				</view>
			</view>
			<view class="box_5 flex-col">
				<text class="text_11">三甲医院</text>
				<view class="section_2 flex-col"></view>
				<view class="section_3 flex-row" @click="gotoHospital">
					<view class="image-text_6 flex-row justify-between">
						<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_6">成都市二环路北四段4号</text>
					</view>
					<view class="image-text_7 flex-row justify-between">
						<view class="block_2 flex-col"></view>
						<view class="block_3 flex-col">
							<text class="text-group_7">成都416医院</text>
							<view class="text-wrapper_4 flex-col">
								<text class="text_9">三甲医院</text>
							</view>
						</view>
					</view>
				</view>
				<view class="section_4 flex-row" @click="gotoHospital">
					<view class="image-text_8 flex-row justify-between">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_8">成都市二环路北二段82号</text>
					</view>
					<view class="image-text_9 flex-row justify-between">
						<view class="group_11 flex-col"></view>
						<view class="group_12 flex-col">
							<text class="text-group_9">成都大学附属医院</text>
							<view class="text-wrapper_5 flex-col">
								<text class="text_10">三甲医院</text>
							</view>
						</view>
					</view>
				</view>
				<view class="section_4 flex-row" @click="gotoHospital">
					<view class="image-text_8 flex-row justify-between">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_8">成都市二环路北二段82号</text>
					</view>
					<view class="image-text_9 flex-row justify-between">
						<view class="group_11 flex-col"></view>
						<view class="group_12 flex-col">
							<text class="text-group_9">成都大学附属医院</text>
							<view class="text-wrapper_5 flex-col">
								<text class="text_10">三甲医院</text>
							</view>
						</view>
					</view>
				</view>
				<view class="section_4 flex-row" @click="gotoHospital">
					<view class="image-text_8 flex-row justify-between">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_8">成都市二环路北二段82号</text>
					</view>
					<view class="image-text_9 flex-row justify-between">
						<view class="group_11 flex-col"></view>
						<view class="group_12 flex-col">
							<text class="text-group_9">成都大学附属医院</text>
							<view class="text-wrapper_5 flex-col">
								<text class="text_10">三甲医院</text>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 悬浮 -->
		<drag-button @btnClick="gotoService" :isDock="true" :existTabBar="true"></drag-button>
		<!-- 弹窗 -->
		<uni-popup class="pop_agreement" ref="popupAgreement" type="bottom" safeArea :mask-click="false">
			<view class="pop_content">
				<view class="section_1 flex-col" style="background-color: #fff">
					<view class="group_7 flex-col">
						<view class="box_10 flex-col"></view>
						<view class="text-wrapper_7">
							<text class="text_12">欢迎使用专业陪诊官方平台！请您在使用前点击</text>
							<text class="text_13" @click="showAgreement">《隐私协议》</text>
							<text class="paragraph_1">
								并仔细阅读，如您同意全部内容，请点击同意开始使用我们的服务。
								<br />
								若点击“不同意”，您将无法使用我们的产品和服务，并会退出本小程序。
							</text>
						</view>
						<text class="text_14">隐私协议</text>
					</view>
					<view class="group_8 flex-row justify-between">
						<view class="text-wrapper_8 flex-col">
							<navigator class="text_15" open-type="exit" target="miniProgram">不同意，退出</navigator>
						</view>
						<view class="text-wrapper_9 flex-col">
							<text class="text_16" @click="agreeAgreement">同意并继续</text>
						</view>
					</view>
				</view>
			</view>
		</uni-popup>
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
			loopData0: [
				{
					lanhuimage0: 'quanchengpeizhen@2x.png',
					lanhutext0: '全程陪诊',
				},
				{
					lanhuimage0: 'daibanmaiyao@2x.png',
					lanhutext0: '待办买药',
				},
				{
					lanhuimage0: 'daibanwenzhen@2x.png',
					lanhutext0: '代办问诊',
				},
				{
					lanhuimage0: 'songqujieguo@2x.png',
					lanhutext0: '送取结果',
				},
				{
					lanhuimage0: 'zunxiangfuwu@2x.png',
					lanhutext0: '尊享服务',
				},
				{
					lanhuimage0: 'yuanneipeihu@2x.png',
					lanhutext0: '院内陪护',
				},
				{
					lanhuimage0: 'daibanchuru@2x.png',
					lanhutext0: '代办出入',
				},
				{
					lanhuimage0: 'zhenqianyuehao@2x.png',
					lanhutext0: '诊前约号',
				},
				{
					lanhuimage0: 'zhenqianyuehao@2x.png',
					lanhutext0: '代取报告',
				},
				{
					lanhuimage0: 'jizhenfuwu@2x.png',
					lanhutext0: '急诊服务',
				},
			],
			loopData1: [
				{
					lanhuimage0: 'https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngefc3c9c19ebe8fb7ea2f546c56aa548c3d0e5cbd6b91855b3aad6d47382cb056',
					lanhutext0: '首页',
					lanhufontColor0: 'rgba(3,182,160,1)',
				},
				{
					lanhuimage0: 'https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng38ddf57f17e05fb63dbb7da810e0e92f154c350f1e82e721e5da3414db22af78',
					lanhutext0: '订单',
					lanhufontColor0: 'rgba(102,102,102,1)',
				},
				{
					lanhuimage0: 'https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngb0a299f892162622844dea9c36ba888aa0c64a45cc2846eeaaf10dbd501879c1',
					lanhutext0: '消息',
					lanhufontColor0: 'rgba(102,102,102,1)',
				},
				{
					lanhuimage0: 'https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng60d05caf502eb47837f95629455272416a922cbe755ef5631c7fff7dbba741f1',
					lanhutext0: '我的',
					lanhufontColor0: 'rgba(102,102,102,1)',
				},
			],
			constants: {},
		}
	},
	methods: {
		agreeAgreement() {
			uni.showTabBar()
			this.$refs.popupAgreement.close()
			uni.setStorageSync('isAgreement', true)
		},

		showAgreement() {
			uni.navigateTo({ url: '/pagesA/pages/privacy_agreement/privacy_agreement' })
		},

		isLogin() {
			let userInfo = uni.getStorageSync('userInfo')
			if (!userInfo) {
				uni.navigateTo({ url: '/pagesA/pages/login/login' })
				return false
			}
			return true
		},

		gotoLocation() {
			uni.navigateTo({ url: '/pagesA/pages/select_city/select_city' })
		},
		gotoDetail() {
			if (!this.isLogin()) {
				return
			}
			uni.navigateTo({ url: '/pagesA/pages/select_hospital/select_hospital' })
		},
		gotoHospital() {
			if (!this.isLogin()) {
				return
			}
			uni.navigateTo({ url: '/pagesA/pages/hospital_detail/hospital_detail' })
		},
		gotoService() {
			if (!this.isLogin()) {
				return
			}
			uni.navigateTo({ url: '/pagesA/pages/customer_service/customer_service' })
		},
	},
	onShow() {
		let isAgreement = uni.getStorageSync('isAgreement')
		//判断协议
		if (!isAgreement) {
			this.$refs.popupAgreement.open()
			uni.hideTabBar()
		}
	},
}
</script>
<style lang="scss" scoped>
.page {
	position: relative;
	width: 750rpx;
	overflow: hidden;
	.box_1 {
		border-radius: 9px;
		position: absolute;
		left: 20rpx;
		top: 188rpx;
		width: 710rpx;
		height: 228rpx;
	}
	.section_1 {
		background-color: rgba(246, 246, 246, 1);
		position: relative;
		.box_3 {
			margin-top: 350rpx;
			padding: 80rpx 76rpx 0rpx 50rpx;
			.block_1 {
				width: 624rpx;
				.image-text_2 {
					width: 142rpx;
					.thumbnail_3 {
						width: 40rpx;
						height: 40rpx;
					}
					.text-group_2 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 4rpx;
					}
				}
				.image-text_3 {
					width: 140rpx;
					.thumbnail_4 {
						width: 40rpx;
						height: 40rpx;
					}
					.text-group_3 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 4rpx;
					}
				}
				.image-text_4 {
					width: 140rpx;
					.thumbnail_5 {
						width: 40rpx;
						height: 40rpx;
					}
					.text-group_4 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 4rpx;
					}
				}
			}
		}
		.box_4 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 5px;
			width: 710rpx;
			align-self: center;
			margin-top: 20rpx;
			padding: 22rpx 20rpx 26rpx 20rpx;
			.image-wrapper_2 {
				width: 670rpx;
				.image_6 {
					width: 326rpx;
					height: 192rpx;
					margin-bottom: 2rpx;
				}
				.image_7 {
					width: 326rpx;
					height: 194rpx;
				}
			}
			.grid_1 {
				width: 624rpx;
				height: 230rpx;
				flex-wrap: wrap;
				margin: 24rpx 26rpx 0 28rpx;
				.image-text_5 {
					width: 96rpx;
					height: 96rpx;
					margin: 0 36rpx 34rpx 0;
					&:nth-child(5n) {
						margin-right: 0;
					}
					&:nth-last-child(-n + 5) {
						margin-bottom: 0;
					}
					.label_2 {
						width: 50rpx;
						height: 50rpx;
						margin: 0 26rpx 0 20rpx;
					}
					.text-group_5 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 12rpx;
					}
				}
			}
		}
		.box_5 {
			position: relative;
			padding: 58rpx 20rpx 20rpx 28rpx;
			.section_2 {
				background-color: rgba(165, 229, 215, 1);
				width: 80rpx;
				height: 20rpx;
				margin: 0 588rpx 0 34rpx;
			}
			.section_3 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 8px;
				position: relative;
				margin-top: 24rpx;
				padding: 126rpx 232rpx 20rpx 186rpx;
				.image-text_6 {
					width: 284rpx;
					.thumbnail_6 {
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
					position: absolute;
					left: 20rpx;
					top: 16rpx;
					width: 322rpx;
					height: 146rpx;
					.block_2 {
						border-radius: 10px;
						background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/ce1f1449ce744cbab4a694a2338c9e2f_mergeImage.png);
						width: 144rpx;
						height: 144rpx;
						margin-top: 2rpx;
					}
					.block_3 {
						margin-bottom: 54rpx;
						.text-group_7 {
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
							margin: 16rpx 46rpx 0 0;
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
			}
			.section_4 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 8px;
				position: relative;
				margin-top: 24rpx;
				padding: 126rpx 218rpx 20rpx 186rpx;
				.image-text_8 {
					width: 298rpx;
					.thumbnail_7 {
						width: 22rpx;
						height: 28rpx;
						margin: 2rpx 0 4rpx 0;
					}
					.text-group_8 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
				}
				.image-text_9 {
					position: absolute;
					left: 20rpx;
					top: 16rpx;
					width: 388rpx;
					height: 146rpx;
					.group_11 {
						border-radius: 10px;
						background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/50e4ba3d7ca54f59a4dc6f03df852fba_mergeImage.png);
						width: 144rpx;
						height: 144rpx;
						margin-top: 2rpx;
					}
					.group_12 {
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
						.text-wrapper_5 {
							background-color: rgba(82, 183, 175, 1);
							border-radius: 3px;
							margin: 16rpx 112rpx 0 0;
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
			}
			.text_11 {
				position: absolute;
				left: 28rpx;
				top: 34rpx;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 34rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: left;
				white-space: nowrap;
				line-height: 48rpx;
			}
			.section_5 {
				// position: fixed;
				box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.12);
				border-radius: 7px;
				position: absolute;
				left: 654rpx;
				top: 250rpx;
				width: 96rpx;
				height: 96rpx;
			}
		}
		.box_6 {
			height: 364rpx;
			background: #5fc3a2;
			background-size: 100% 100%;
			width: 750rpx;
			position: absolute;
			left: 0;
			top: 0;
			padding: 72rpx 10rpx 210rpx 22rpx;
			.block_4 {
				margin: 0 18rpx 0 20rpx;
				height: 34rpx;
			}
			.block_5 {
				margin-top: 28rpx;
				.label_3 {
					width: 48rpx;
					height: 50rpx;
					margin: 6rpx 0 4rpx 0;
				}
				.text_14 {
					overflow-wrap: break-word;
					color: rgba(255, 255, 255, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin: 12rpx 0 0 10rpx;
				}
				.thumbnail_10 {
					width: 8rpx;
					height: 16rpx;
					margin: 22rpx 0 22rpx 10rpx;
				}
				.text_15 {
					overflow-wrap: break-word;
					color: rgba(255, 255, 255, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: right;
					white-space: nowrap;
					line-height: 48rpx;
					margin-left: 138rpx;
				}
				.image_9 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 136rpx;
				}
			}
		}
		.box_7 {
			box-shadow: 0px -4px 10px 0px rgba(0, 0, 0, 0.09);
			background-color: rgba(254, 255, 255, 1);
			position: absolute;
			left: 0;
			top: 1464rpx;
			width: 750rpx;
			height: 160rpx;
			padding: 26rpx 70rpx 18rpx 70rpx;
			.list_2 {
				width: 610rpx;
				height: 84rpx;
				justify-content: space-between;
				.image-text_10 {
					margin-right: 140rpx;
					.label_4 {
						width: 44rpx;
						height: 44rpx;
						align-self: center;
					}
					.text-group_10 {
						overflow-wrap: break-word;
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 6rpx;
					}
				}
			}
			.image_10 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 22rpx;
			}
		}
	}
}
.pop_content {
	.section_1 {
		border-radius: 17px 17px 0px 0px;
		padding: 34rpx 42rpx 50rpx 42rpx;
		.group_7 {
			background-color: rgba(255, 255, 255, 1);
			position: relative;
			margin-right: 16rpx;
			padding: 26rpx 0 12rpx 2rpx;
			.box_10 {
				background-color: rgba(168, 226, 215, 1);
				border-radius: 5px;
				width: 62rpx;
				height: 18rpx;
				margin: 0 544rpx 0 46rpx;
			}
			.text-wrapper_7 {
				width: 668rpx;
				height: 220rpx;
				overflow-wrap: break-word;
				font-size: 0;
				font-weight: normal;
				text-align: left;
				line-height: 44rpx;
				margin: 64rpx -16rpx 0 0;
				.text_12 {
					width: 668rpx;
					height: 220rpx;
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 44rpx;
				}
				.text_13 {
					width: 668rpx;
					height: 220rpx;
					overflow-wrap: break-word;
					color: rgba(80, 186, 174, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 44rpx;
				}
				.paragraph_1 {
					width: 668rpx;
					height: 220rpx;
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 44rpx;
				}
			}
			.text_14 {
				position: absolute;
				left: 0;
				top: 6rpx;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 34rpx;
				letter-spacing: 2px;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: center;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.group_8 {
			width: 670rpx;
			margin-top: 46rpx;
			.text-wrapper_8 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 19px;
				border: 1px solid rgba(215, 215, 215, 1);
				padding: 16rpx 62rpx 14rpx 64rpx;
				.text_15 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
			.text-wrapper_9 {
				background-color: rgba(80, 186, 174, 1);
				border-radius: 19px;
				padding: 18rpx 100rpx 16rpx 102rpx;
				.text_16 {
					overflow-wrap: break-word;
					color: rgba(255, 255, 255, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
		}
	}
}
</style>
