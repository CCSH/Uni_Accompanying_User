<template>
	<view class="page flex-col">
		<view class="block_1 flex-col">
			<view class="group_4 flex-col">
				<view class="section_1 flex-row">
					<view class="box_2 flex-col">
						<view class="text-wrapper_2 flex-col">
							<text class="text_4">陪诊&nbsp;我们更用心</text>
						</view>
					</view>
					<view class="text-group_2 flex-col">
						<text class="text_5">王红红</text>
						<view class="text-wrapper_3">
							<text class="text_6">服务单数：</text>
							<text class="text_7">81</text>
						</view>
						<view class="text-wrapper_4">
							<text class="text_8">成都市，</text>
							<text class="text_9">11.4km</text>
						</view>
					</view>
					<view class="text-wrapper_5">
						<text class="text_10">评价：</text>
						<text class="text_11">51</text>
					</view>
				</view>
				<view class="text-wrapper_13 flex-row justify-between">
					<text class="text_12">经验介绍：</text>
					<text class="text_13">我是一名全职陪诊师，每天穿梭在成都各三甲医院，陪同患者就医，我性格比较阳光开朗，有爱心、耐心、责任心，我比较喜欢中国传统文化也喜欢中医知识。</text>
				</view>
			</view>
			<view class="section_2 flex-col">
				<view class="group_6 flex-row justify-end">
					<view class="box_11 flex-col"></view>
					<text class="text_14" @click="gotoComment">49条评论</text>
					<image class="thumbnail_4" referrerpolicy="no-referrer" src="/static/more_lv@2x.png" />
					<text class="text_27">服务项目</text>
				</view>
				<image class="image_5" referrerpolicy="no-referrer" src="" />
				<view class="group_7 flex-row justify-between">
					<view class="image-text_1 flex-row justify-between">
						<view class="box_12 flex-col"></view>
						<view class="text-group_3 flex-col">
							<view class="text-wrapper_14 flex-row justify-between">
								<text class="text_28">全程陪诊</text>
								<text class="text_15">￥300.00/次</text>
							</view>
							<text class="text_29">全程陪同服务，手续代办服务</text>
						</view>
					</view>
					<view class="text-wrapper_7 flex-col" @click="gotoServe">
						<text class="text_16">去预约</text>
					</view>
				</view>
				<image class="image_6" referrerpolicy="no-referrer" src="" />
				<view class="group_8 flex-row justify-between">
					<view class="image-text_2 flex-row justify-between">
						<view class="section_3 flex-col"></view>
						<view class="text-group_4 flex-col">
							<view class="text-wrapper_15 flex-row justify-between">
								<text class="text_30">代办买药</text>
								<text class="text_17">￥150.00/次</text>
							</view>
							<text class="text_31">人工排队代买药服务</text>
						</view>
					</view>
					<view class="text-wrapper_8 flex-col" @click="gotoServe">
						<text class="text_18">去预约</text>
					</view>
				</view>
				<image class="image_7" referrerpolicy="no-referrer" src="" />
				<view class="group_9 flex-row justify-between">
					<view class="image-text_3 flex-row justify-between">
						<view class="box_13 flex-col"></view>
						<view class="text-group_5 flex-col">
							<view class="text-wrapper_16 flex-row justify-between">
								<text class="text_32">代办问诊</text>
								<text class="text_19">￥200.00/次</text>
							</view>
							<text class="text_33">代客户到机构咨询及代开检查单服务</text>
						</view>
					</view>
					<view class="text-wrapper_9 flex-col" @click="gotoServe">
						<text class="text_20">去预约</text>
					</view>
				</view>
				<image class="image_8" referrerpolicy="no-referrer" src="" />
				<view class="group_10 flex-row justify-between">
					<view class="image-text_4 flex-row justify-between">
						<view class="block_2 flex-col"></view>
						<view class="text-group_6 flex-col">
							<view class="text-wrapper_17 flex-row justify-between">
								<text class="text_34">送取结果</text>
								<text class="text_21">￥150.00/次</text>
							</view>
							<text class="text_35">送/取结果快递到家服务，服务仅…</text>
						</view>
					</view>
					<view class="text-wrapper_10 flex-col" @click="gotoServe">
						<text class="text_22">去预约</text>
					</view>
				</view>
				<image class="image_9" referrerpolicy="no-referrer" src="" />
				<view class="group_11 flex-row justify-between">
					<view class="image-text_5 flex-row justify-between">
						<view class="section_4 flex-col"></view>
						<view class="text-group_7 flex-col">
							<view class="text-wrapper_18 flex-row justify-between">
								<text class="text_36">尊享服务</text>
								<text class="text_23">￥300.00/次</text>
							</view>
							<text class="text_37">组合套餐项目升级包</text>
						</view>
					</view>
					<view class="text-wrapper_11 flex-col" @click="gotoServe">
						<text class="text_24">去预约</text>
					</view>
				</view>
				<image class="image_10" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng328329fc7006c549aea6de621b481d31b6d577e1306155e4d4dfbe07f659c7ba" />
				<image class="image_11" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng5a55bce0e61824e6b35e82f487c8fc2828194ab82d71f586b93de2f8b36bc031" />
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
		gotoServe() {
			uni.navigateTo({ url: '/pagesA/pages/service_detail/service_detail' })
		},
		gotoComment() {
			uni.navigateTo({ url: '/pagesA/pages/comment_list/comment_list' })
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
	.block_1 {
		background-color: rgba(246, 246, 246, 1);
		.group_1 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.box_9 {
				margin: 0 18rpx 0 2rpx;
				.text-wrapper_12 {
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
					.text_25 {
						overflow-wrap: break-word;
						color: rgba(255, 255, 255, 1);
						font-size: 28rpx;
						font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_26 {
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
			.box_10 {
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
			background-color: rgba(255, 255, 255, 1);
			border-radius: 10px;
			width: 702rpx;
			align-self: center;
			margin-top: 26rpx;
			padding: 20rpx 24rpx 40rpx 20rpx;
			.section_1 {
				margin-right: 164rpx;
				.box_2 {
					border-radius: 8px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/2ca939baa8544631979e7c40f429ca17_mergeImage.png);
					padding-top: 120rpx;
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
				.text-group_2 {
					margin: 0 0 10rpx 20rpx;
					.text_5 {
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
					.text-wrapper_3 {
						width: 170rpx;
						height: 40rpx;
						overflow-wrap: break-word;
						font-size: 0;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 10rpx 28rpx 0 0;
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
						width: 198rpx;
						height: 40rpx;
						overflow-wrap: break-word;
						font-size: 0;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-top: 12rpx;
						.text_8 {
							overflow-wrap: break-word;
							color: rgba(80, 186, 174, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
						.text_9 {
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
				.text-wrapper_5 {
					width: 114rpx;
					height: 40rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin: 58rpx 0 62rpx 2rpx;
					.text_10 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_11 {
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
			.text-wrapper_13 {
				width: 656rpx;
				margin: 20rpx 0 0 2rpx;
				.text_12 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
				.text_13 {
					width: 516rpx;
					height: 160rpx;
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 40rpx;
				}
			}
		}
		.section_2 {
			background-color: rgba(255, 255, 255, 1);
			margin-top: 28rpx;
			padding: 56rpx 0 18rpx 0;
			.group_6 {
				position: relative;
				width: 668rpx;
				margin: 0 42rpx 0 40rpx;
				padding: 14rpx 0 0 28rpx;
				.box_11 {
					background-color: rgba(165, 229, 215, 1);
					width: 80rpx;
					height: 20rpx;
					margin: 12rpx 0 8rpx 0;
				}
				.text_14 {
					overflow-wrap: break-word;
					color: rgba(80, 186, 174, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 422rpx;
				}
				.thumbnail_4 {
					width: 8rpx;
					height: 20rpx;
					margin: 10rpx 0 10rpx 12rpx;
				}
				.text_27 {
					position: absolute;
					left: 0;
					top: 0;
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: right;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
			.image_5 {
				width: 750rpx;
				height: 2rpx;
				margin-top: 44rpx;
				background: #dcdcdc;
			}
			.group_7 {
				width: 672rpx;
				margin: 38rpx 40rpx 0 38rpx;
				.image-text_1 {
					width: 410rpx;
					.box_12 {
						border-radius: 3px;
						background-image: url(/static/quanchengpeizhen2@2x.png);
						width: 80rpx;
						height: 80rpx;
						margin-bottom: 2rpx;
						background-size: cover;
					}
					.text-group_3 {
						margin-top: 4rpx;
						.text-wrapper_14 {
							width: 302rpx;
							margin-right: 10rpx;
							.text_28 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 28rpx;
								font-family: PingFangSC-Medium;
								font-weight: 500;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
								margin-top: 2rpx;
							}
							.text_15 {
								overflow-wrap: break-word;
								color: rgba(255, 88, 94, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text_29 {
							overflow-wrap: break-word;
							color: rgba(102, 102, 102, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
							margin-top: 2rpx;
						}
					}
				}
				.text-wrapper_7 {
					background-color: rgba(80, 186, 174, 1);
					border-radius: 15px;
					margin: 12rpx 0 10rpx 0;
					padding: 10rpx 28rpx 10rpx 28rpx;
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
			.image_6 {
				width: 676rpx;
				height: 4rpx;
				margin: 36rpx 38rpx 0 36rpx;
				background: #e6e6e6;
			}
			.group_8 {
				width: 672rpx;
				margin: 36rpx 40rpx 0 38rpx;
				.image-text_2 {
					width: 394rpx;
					.section_3 {
						border-radius: 3px;
						background-image: url(/static/daibanmaiyao2@2x.png);
						width: 80rpx;
						height: 80rpx;
						margin-bottom: 2rpx;
						background-size: cover;
					}
					.text-group_4 {
						margin-top: 4rpx;
						.text-wrapper_15 {
							width: 294rpx;
							margin-left: 2rpx;
							.text_30 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 28rpx;
								font-family: PingFangSC-Medium;
								font-weight: 500;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
								margin-top: 2rpx;
							}
							.text_17 {
								overflow-wrap: break-word;
								color: rgba(255, 88, 94, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text_31 {
							overflow-wrap: break-word;
							color: rgba(102, 102, 102, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
							margin: 2rpx 80rpx 0 0;
						}
					}
				}
				.text-wrapper_8 {
					background-color: rgba(80, 186, 174, 1);
					border-radius: 15px;
					margin: 10rpx 0 12rpx 0;
					padding: 10rpx 28rpx 10rpx 28rpx;
					.text_18 {
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
			.image_7 {
				width: 676rpx;
				height: 4rpx;
				margin: 38rpx 38rpx 0 36rpx;
				background: #e6e6e6;
			}
			.group_9 {
				width: 672rpx;
				margin: 34rpx 40rpx 0 38rpx;
				.image-text_3 {
					width: 482rpx;
					.box_13 {
						border-radius: 3px;
						background-image: url(/static/daibanwenzhen2@2x.png);
						width: 80rpx;
						height: 80rpx;
						margin-bottom: 2rpx;
						background-size: cover;
					}
					.text-group_5 {
						margin-top: 4rpx;
						.text-wrapper_16 {
							width: 300rpx;
							margin: 0 82rpx 0 2rpx;
							.text_32 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 28rpx;
								font-family: PingFangSC-Medium;
								font-weight: 500;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
							.text_19 {
								overflow-wrap: break-word;
								color: rgba(255, 88, 94, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text_33 {
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
				.text-wrapper_9 {
					background-color: rgba(80, 186, 174, 1);
					border-radius: 15px;
					margin: 16rpx 0 6rpx 0;
					padding: 10rpx 28rpx 10rpx 28rpx;
					.text_20 {
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
			.image_8 {
				width: 674rpx;
				height: 4rpx;
				margin: 36rpx 40rpx 0 36rpx;
				background: #e6e6e6;
			}
			.group_10 {
				width: 672rpx;
				margin: 36rpx 40rpx 0 38rpx;
				.image-text_4 {
					width: 470rpx;
					.block_2 {
						border-radius: 3px;
						background-image: url(/static/qusongjieguo2@2x.png);
						width: 80rpx;
						height: 80rpx;
						margin-bottom: 2rpx;
						background-size: cover;
					}
					.text-group_6 {
						margin-top: 4rpx;
						.text-wrapper_17 {
							width: 296rpx;
							margin-right: 76rpx;
							.text_34 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 28rpx;
								font-family: PingFangSC-Medium;
								font-weight: 500;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
								margin-top: 2rpx;
							}
							.text_21 {
								overflow-wrap: break-word;
								color: rgba(255, 88, 94, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text_35 {
							overflow-wrap: break-word;
							color: rgba(102, 102, 102, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
							margin-top: 2rpx;
						}
					}
				}
				.text-wrapper_10 {
					background-color: rgba(80, 186, 174, 1);
					border-radius: 15px;
					margin: 14rpx 0 8rpx 0;
					padding: 10rpx 28rpx 10rpx 28rpx;
					.text_22 {
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
			.image_9 {
				width: 674rpx;
				height: 4rpx;
				margin: 40rpx 40rpx 0 36rpx;
				background: #e6e6e6;
			}
			.group_11 {
				width: 672rpx;
				margin: 34rpx 40rpx 0 38rpx;
				.image-text_5 {
					width: 400rpx;
					.section_4 {
						border-radius: 3px;
						background-image: url(/static/xunxiangfuwu2@2x.png);
						width: 80rpx;
						height: 80rpx;
						background-size: cover;
					}
					.text-group_7 {
						margin-top: 4rpx;
						.text-wrapper_18 {
							width: 302rpx;
							.text_36 {
								overflow-wrap: break-word;
								color: rgba(51, 51, 51, 1);
								font-size: 28rpx;
								font-family: PingFangSC-Medium;
								font-weight: 500;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
							.text_23 {
								overflow-wrap: break-word;
								color: rgba(255, 88, 94, 1);
								font-size: 28rpx;
								font-weight: normal;
								text-align: left;
								white-space: nowrap;
								line-height: 40rpx;
							}
						}
						.text_37 {
							overflow-wrap: break-word;
							color: rgba(102, 102, 102, 1);
							font-size: 24rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 34rpx;
							margin: 2rpx 86rpx 0 0;
						}
					}
				}
				.text-wrapper_11 {
					background-color: rgba(80, 186, 174, 1);
					border-radius: 15px;
					margin: 14rpx 0 6rpx 0;
					padding: 10rpx 28rpx 10rpx 28rpx;
					.text_24 {
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
			.image_10 {
				width: 674rpx;
				height: 4rpx;
				margin: 34rpx 40rpx 0 36rpx;
			}
			.image_11 {
				width: 268rpx;
				height: 10rpx;
				align-self: center;
				margin-top: 20rpx;
			}
		}
	}
}
</style>
