<template>
	<view class="page flex-col">
		<view class="group_1 flex-col">
			<view class="section_5 flex-col">
				<view class="box_3 flex-row">
					<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/sousuo@2x.png" />
					<input class="image-text_2 flex-row justify-between text-group_1" placeholder="搜索" />
				</view>
				<view class="list_2 flex-col">
					<view class="list-items_1 flex-col" v-for="(item, index) in loopData0" :key="index" @click="gotoDetail">
						<view class="section_6 flex-row">
							<image class="section_1 flex-col" :src="item.lanhuBg2">
								<view class="text-wrapper_2 flex-col">
									<!-- <text class="text_4" :html="item.lanhutext0"></text> -->
								</view>
							</image>
							<view v-if="item.slot3 === 3" class="section_7 flex-col">
								<text class="text_5">{{ item.specialSlot3.lanhutext0 }}</text>
								<view class="group_4 flex-row justify-between">
									<view class="text-wrapper_3">
										<text class="text_6">{{ item.specialSlot3.lanhutext1 }}</text>
										<text class="text_7">{{ item.specialSlot3.lanhutext2 }}</text>
									</view>
									<view class="text-wrapper_4">
										<text class="text_8">{{ item.specialSlot3.lanhutext3 }}</text>
										<text class="text_9">{{ item.specialSlot3.lanhutext4 }}</text>
									</view>
								</view>
								<view class="text-wrapper_5">
									<text class="text_10">{{ item.specialSlot3.lanhutext5 }}</text>
									<text class="text_11">{{ item.specialSlot3.lanhutext6 }}</text>
								</view>
							</view>
							<view v-if="item.slot1 === 1" class="text-group_3 flex-col">
								<text class="text_12">{{ item.specialSlot1.lanhutext0 }}</text>
								<view class="text-wrapper_6">
									<text class="text_13">{{ item.specialSlot1.lanhutext1 }}</text>
									<text class="text_14">{{ item.specialSlot1.lanhutext2 }}</text>
								</view>
								<view class="text-wrapper_7">
									<text class="text_15">{{ item.specialSlot1.lanhutext3 }}</text>
									<text class="text_16">{{ item.specialSlot1.lanhutext4 }}</text>
								</view>
							</view>
							<view v-if="item.slot2 === 2" class="text-wrapper_8">
								<text class="text_17">{{ item.specialSlot2.lanhutext0 }}</text>
								<text class="text_18">{{ item.specialSlot2.lanhutext1 }}</text>
							</view>
							<view class="text-wrapper_9 flex-col" @click="goto">
								<text class="text_19">{{ item.lanhutext1 }}</text>
							</view>
						</view>
						<view class="text-wrapper_12 flex-row justify-between">
							<text class="text_20">{{ item.lanhutext2 }}</text>
							<text class="text_21">{{ item.lanhutext3 }}</text>
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
			loopData0: [
				{
					lanhuBg2: '/static/touxiang_a@2x.png',
					lanhutext0: '陪诊&nbsp;我们更用心',
					lanhutext1: '去下单',
					lanhutext2: '经验介绍：',
					lanhutext3: '我是一名全职陪诊师',
					specialSlot1: {
						lanhutext0: '王红红',
						lanhutext1: '服务单数：',
						lanhutext2: '81',
						lanhutext3: '成都市，',
						lanhutext4: '11.4km',
					},
					slot1: 1,
					specialSlot2: { lanhutext0: '评价：', lanhutext1: '51' },
					slot2: 2,
				},
				{
					lanhuBg2: '/static/touxiang_a@2x.png',
					lanhutext0: '陪诊&nbsp;我们更用心',
					lanhutext1: '去下单',
					lanhutext2: '经验介绍：',
					lanhutext3: '我是一名全职陪诊师，每天穿梭在成都各三甲医院，陪同患者就医…',
					specialSlot1: {
						lanhutext0: '李云溪',
						lanhutext1: '服务单数：',
						lanhutext2: '81',
						lanhutext3: '成都市，',
						lanhutext4: '11.9km',
					},
					slot1: 1,
					specialSlot2: { lanhutext0: '评价：', lanhutext1: '51' },
					slot2: 2,
				},
				{
					lanhuBg2: '/static/touxiang_a@2x.png',
					lanhutext0: '陪诊&nbsp;我们更用心',
					lanhutext1: '去下单',
					lanhutext2: '经验介绍：',
					lanhutext3: '我是一名全职陪诊师，每天穿梭在成都各三甲医院，陪同患者就医…',
					specialSlot3: {
						lanhutext0: '罗佳丽',
						lanhutext1: '服务单数：',
						lanhutext2: '81',
						lanhutext3: '评价：',
						lanhutext4: '51',
						lanhutext5: '成都市，',
						lanhutext6: '12.9km',
					},
					slot3: 3,
				},
				{
					lanhuBg2: '/static/touxiang_a@2x.png',
					lanhutext0: '陪诊&nbsp;我们更用心',
					lanhutext1: '去下单',
					lanhutext2: '经验介绍：',
					lanhutext3: '我是一名全职陪诊师，每天穿梭在成都各三甲医院，陪同患者就医…',
					specialSlot3: {
						lanhutext0: '世杰',
						lanhutext1: '服务单数：',
						lanhutext2: '81',
						lanhutext3: '评价：',
						lanhutext4: '51',
						lanhutext5: '成都市，',
						lanhutext6: '15.9km',
					},
					slot3: 3,
				},
			],
			constants: {},
		}
	},
	methods: {

    gotoDetail(){
      uni.navigateTo({ url: '/pagesA/pages/personnel_detail/personnel_detail' })
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
	.group_1 {
		background-color: rgba(246, 246, 246, 1);
		height: 1624rpx;
		.box_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.section_3 {
				margin: 0 18rpx 0 2rpx;
				.text-wrapper_11 {
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
					.text_22 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_23 {
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
					margin: 2rpx 0 10rpx 10rpx;
				}
				.image_4 {
					width: 50rpx;
					height: 24rpx;
					margin: 2rpx 0 8rpx 10rpx;
				}
			}
			.section_4 {
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
					margin-left: 260rpx;
				}
				.image_2 {
					width: 160rpx;
					height: 60rpx;
					margin-left: 154rpx;
				}
			}
		}
		.section_5 {
			padding: 26rpx 20rpx 20rpx 24rpx;
			.box_3 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 15px;
				border: 1px solid rgba(225, 225, 225, 1);
				margin-right: 4rpx;
				padding: 8rpx 20rpx 8rpx 20rpx;
				.thumbnail_7 {
					width: 26rpx;
					height: 30rpx;
					margin: 6rpx 10rpx 4rpx 0;
				}
				.image-text_2 {
					width: 600rpx !important;

					// .text-group_1 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					// }
				}
			}
			.list_2 {
				height: 1272rpx;
				margin-top: 26rpx;
				.list-items_1 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 10px;
					width: 702rpx;
					// height: 300rpx;
					margin: 0 4rpx 24rpx 0;
					padding: 20rpx 24rpx 20rpx 20rpx;
					.section_6 {
						position: relative;
						width: 658rpx;
						height: 160rpx;
						.section_1 {
							width: 160rpx;
							height: 160rpx;
							border-radius: 8px;
							// padding-top: 120rpx;
							background-size: cover;
							overflow: hidden;
							.text-wrapper_2 {
								background-color: rgba(80, 186, 174, 1);
								border-radius: 0px 0px 8px 8px;
								padding: 4rpx 4rpx 8rpx 8rpx;
								.text_4 {
									overflow-wrap: break-word;
									color: rgba(255, 255, 255, 1);
									font-size: 20rpx;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 28rpx;
								}
							}
						}
						.section_7 {
							position: absolute;
							left: 182rpx;
							top: 0;
							.text_5 {
								width: 102rpx;
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 34rpx;
								font-family: PingFangSC-Semibold;
								font-weight: 600;
								text-align: right;
								white-space: nowrap;
								line-height: 48rpx;
								margin: 0 210rpx 0 2rpx;
							}
							.group_4 {
								width: 314rpx;
								margin-top: 10rpx;
								.text-wrapper_3 {
									width: 170rpx;
									height: 40rpx;
									overflow-wrap: break-word;
									font-size: 0;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 40rpx;
									.text_6 {
										overflow-wrap: break-word;
										color: rgba(51, 51, 51, 1);
										font-size: 28rpx;
										font-weight: normal;
										text-align: left;
										white-space: nowrap;
										line-height: 40rpx;
									}
									.text_7 {
										overflow-wrap: break-word;
										color: rgba(103, 189, 180, 1);
										font-size: 28rpx;
										font-weight: normal;
										text-align: left;
										white-space: nowrap;
										line-height: 40rpx;
									}
								}
								.text-wrapper_4 {
									width: 114rpx;
									height: 40rpx;
									overflow-wrap: break-word;
									font-size: 0;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 40rpx;
									.text_8 {
										overflow-wrap: break-word;
										color: rgba(51, 51, 51, 1);
										font-size: 28rpx;
										font-weight: normal;
										text-align: left;
										white-space: nowrap;
										line-height: 40rpx;
									}
									.text_9 {
										overflow-wrap: break-word;
										color: rgba(103, 189, 180, 1);
										font-size: 28rpx;
										font-weight: normal;
										text-align: left;
										white-space: nowrap;
										line-height: 40rpx;
									}
								}
							}
							.text-wrapper_5 {
								width: 204rpx;
								height: 40rpx;
								overflow-wrap: break-word;
								font-size: 0;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
								margin: 12rpx 110rpx 0 0;
								.text_10 {
									overflow-wrap: break-word;
									color: rgba(80, 186, 174, 1);
									font-size: 28rpx;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 40rpx;
								}
								.text_11 {
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
						.text-group_3 {
							position: absolute;
							left: 180rpx;
							top: 0;
							.text_12 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 34rpx;
								font-family: PingFangSC-Semibold;
								font-weight: 600;
								text-align: right;
								white-space: nowrap;
								line-height: 48rpx;
								margin-right: 96rpx;
							}
							.text-wrapper_6 {
								width: 170rpx;
								height: 40rpx;
								overflow-wrap: break-word;
								font-size: 0;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
								margin: 10rpx 28rpx 0 0;
								.text_13 {
									overflow-wrap: break-word;
									color: rgba(51, 51, 51, 1);
									font-size: 28rpx;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 40rpx;
								}
								.text_14 {
									overflow-wrap: break-word;
									color: rgba(103, 189, 180, 1);
									font-size: 28rpx;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 40rpx;
								}
							}
							.text-wrapper_7 {
								width: 198rpx;
								height: 40rpx;
								overflow-wrap: break-word;
								font-size: 0;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
								margin-top: 12rpx;
								.text_15 {
									overflow-wrap: break-word;
									color: rgba(80, 186, 174, 1);
									font-size: 28rpx;
									font-weight: normal;
									text-align: left;
									white-space: nowrap;
									line-height: 40rpx;
								}
								.text_16 {
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
						.text-wrapper_8 {
							position: absolute;
							left: 380rpx;
							top: 58rpx;
							width: 114rpx;
							height: 40rpx;
							overflow-wrap: break-word;
							font-size: 0;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
							.text_17 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
							.text_18 {
								overflow-wrap: break-word;
								color: rgba(103, 189, 180, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text-wrapper_9 {
							background-color: rgba(80, 186, 174, 1);
							border-radius: 15px;
							margin: 100rpx 0 0 358rpx;
							padding: 10rpx 28rpx 10rpx 28rpx;
							.text_19 {
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
					.text-wrapper_12 {
						width: 656rpx;
            height: auto;
						margin: 20rpx 0 0 2rpx;
						.text_20 {
							overflow-wrap: break-word;
							color: rgba(51, 51, 51, 1);
							font-size: 28rpx;
							font-family: PingFangSC-Semibold;
							font-weight: 600;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
						.text_21 {
              overflow: hidden;
							width: 516rpx;
							max-height: 80rpx;
							overflow-wrap: break-word;
							color: rgba(51, 51, 51, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							line-height: 40rpx;
						}
					}
				}
			}
			.image_5 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 36rpx;
			}
		}
	}
}
</style>
