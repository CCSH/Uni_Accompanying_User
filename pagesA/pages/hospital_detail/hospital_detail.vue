<template>
  <view class="page flex-col">
    <view class="group_2 flex-col">
      <view class="box_6 flex-col">
        <view class="text-wrapper_12 flex-col">
          <text class="text_23">成都大学附属医院</text>
        </view>
      </view>
      <view class="box_7 flex-col">
        <view class="section_8 flex-row">
          <view class="group_3 flex-col"></view>
          <text class="text_24">选择服务项目</text>
        </view>
        <view class="section_9 flex-row justify-between">
          <view class="image-text_7 flex-row justify-between">
            <view class="group_4 flex-col"></view>
            <view class="text-group_7 flex-col">
              <text class="text_25">代办买药</text>
              <text class="text_26">人工排队代买药服务</text>
            </view>
          </view>
          <view class="section_3 flex-col">
            <view class="text-wrapper_3">
              <text class="text_5">￥168.00</text>
              <text class="text_6">/</text>
              <text class="text_7">&nbsp;次</text>
            </view>
            <view class="text-wrapper_4 flex-col">
              <text class="text_8" @click="gotoServe">去预约</text>
            </view>
          </view>
        </view>
        <image
          class="image_4"
          referrerpolicy="no-referrer"
          src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng4c7c44b66b27174dedc304a2088c388059d7cd01b3cd13a0b1c4c88db4b03f62"
        />
        <view class="section_10 flex-row justify-between">
          <view class="image-text_8 flex-row justify-between">
            <view class="group_5 flex-col"></view>
            <view class="text-group_8 flex-col">
              <text class="text_27">代办问诊</text>
              <text class="text_28">代客户到机构咨询及代开…</text>
            </view>
          </view>
          <view class="section_4 flex-col">
            <view class="text-wrapper_5">
              <text class="text_9">￥168.00</text>
              <text class="text_10">/</text>
              <text class="text_11">&nbsp;次</text>
            </view>
            <view class="text-wrapper_6 flex-col">
              <text class="text_12" @click="gotoServe">去预约</text>
            </view>
          </view>
        </view>
        <image
          class="image_5"
          referrerpolicy="no-referrer"
          src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng4c7c44b66b27174dedc304a2088c388059d7cd01b3cd13a0b1c4c88db4b03f62"
        />
        <view class="section_11 flex-row justify-between">
          <view class="image-text_9 flex-row justify-between">
            <view class="group_6 flex-col"></view>
            <view class="text-group_9 flex-col">
              <text class="text_29">送取结果</text>
              <text class="text_30">送/取结果快递到家服务…</text>
            </view>
          </view>
          <view class="section_5 flex-col">
            <view class="text-wrapper_7">
              <text class="text_13">￥78.00</text>
              <text class="text_14">/</text>
              <text class="text_15">&nbsp;次</text>
            </view>
            <view class="text-wrapper_8 flex-col">
              <text class="text_16" @click="gotoServe">去预约</text>
            </view>
          </view>
        </view>
        <image
          class="image_6"
          referrerpolicy="no-referrer"
          src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng4c7c44b66b27174dedc304a2088c388059d7cd01b3cd13a0b1c4c88db4b03f62"
        />
        <view class="section_12 flex-row">
          <view class="image-text_10 flex-row justify-between">
            <view class="text-group_10 flex-col">
              <text class="text_31">全程陪诊</text>
              <text class="text_32">全程陪同服务，手续代办…</text>
            </view>
            <view class="section_6 flex-col">
              <view class="text-wrapper_9">
                <text class="text_17">￥268.00</text>
                <text class="text_18">/</text>
                <text class="text_19">&nbsp;次</text>
              </view>
              <view class="text-wrapper_10 flex-col">
                <text class="text_20" @click="gotoServe">去预约</text>
              </view>
            </view>
          </view>
          <view class="image-text_11 flex-row justify-between">
            <view class="section_7 flex-col"></view>
            <view class="text-group_11 flex-col">
              <text class="text_31">全程陪诊</text>
              <text class="text_32">全程陪同服务，手续代办…</text>
            </view>
          </view>
        </view>
        <image
          class="image_10"
          referrerpolicy="no-referrer"
          src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng5a55bce0e61824e6b35e82f487c8fc2828194ab82d71f586b93de2f8b36bc031"
        />
        <!-- <view class="image-wrapper_1 flex-col">
          <image
            class="label_1"
            referrerpolicy="no-referrer"
            src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng29194a70c34caf26053288a1ffc56c6b6d098f4e6216d7726e5f81250c7e2c3c"
          />
        </view> -->
        		<!-- 悬浮 -->
		<drag-button @btnClick="gotoService" :isDock="true" :existTabBar="false"></drag-button>
      </view>
      <view class="box_13 flex-col">
        <view class="text-wrapper_13 flex-col">
          <text class="text_33">三甲医院</text>
        </view>
        <view class="image-text_12 flex-row justify-between">
          <image
            class="thumbnail_6"
            referrerpolicy="no-referrer"
            src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngc25db2bb580e9f61fec72131aa9770d3ea337d862d0d5d0553bd45eeb06b55d7"
          />
          <text class="text-group_6">成都市武侯区一环路西一段132号</text>
        </view>
        <image
          class="image_8"
          referrerpolicy="no-referrer"
          src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngf890201bb428659b6976b70f09a688b7e5138a4d97623fb855ae3c075be545b0"
        />
        <text class="text_34">
          成都大学附属医院坐落于成都市北部新城，占地522亩，由本部和附匡口腔医院组成。是西南地区占地面积较大、绿化覆盖最高的园林式生态医院。医院诞生于土地革命战争时期，前身是贺龙元帅领导的第二1
        </text>
        <view class="group_7 flex-row" @click="isOpen = !isOpen">
          <text class="text_35">{{isOpen ? '收起更多':'查看更多'}}</text>
          <image
            class="thumbnail_7"
            referrerpolicy="no-referrer"
            :src="isOpen ? '/static/more_shang@2x.png' : '/static/more_xia@2x.png'"
          />
          <image
            class="thumbnail_8"
            referrerpolicy="no-referrer"
            src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPngb3e6152346f8b84162179926db3a605e3732005106102e8bf41fdebca40791fa"
          />
        </view>
        <view class="group_8 flex-col"></view>
      </view>
    </view>
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
      isOpen:false,
      constants: {},
    };
  },
  methods: {
    gotoServe() {
      uni.navigateTo({ url: '/pagesA/pages/service_detail/service_detail' })
    }
  },
};
</script>
<style scoped lang="scss">
.page {
  position: relative;
  width: 750rpx;
  // height: 1624rpx;
  padding-bottom: 40rpx;
  overflow: hidden;
  .group_2 {
    background-color: rgba(246, 246, 246, 1);
    position: relative;
    .box_1 {
      background-color: rgba(81, 187, 164, 1);
      padding: 30rpx 10rpx 22rpx 40rpx;
      .box_14 {
        margin: 0 18rpx 0 2rpx;
        .text-wrapper_14 {
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
          .text_36 {
            overflow-wrap: break-word;
            color: rgba(255, 255, 255, 1);
            font-size: 28rpx;
            font-family: Helvetica, 'Microsoft YaHei', Arial, sans-serif;
            font-weight: normal;
            text-align: left;
            white-space: nowrap;
            line-height: 34rpx;
          }
          .text_37 {
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
        .thumbnail_9 {
          width: 34rpx;
          height: 22rpx;
          margin: 4rpx 0 8rpx 438rpx;
        }
        .thumbnail_10 {
          width: 30rpx;
          height: 22rpx;
          margin: 4rpx 0 8rpx 10rpx;
        }
        .image_9 {
          width: 50rpx;
          height: 24rpx;
          margin: 2rpx 0 8rpx 10rpx;
        }
      }
      .box_15 {
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
    .box_6 {
      background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/1493eb6397054ed3b6d598eeeba1ff8d_mergeImage.png);
      padding: 132rpx 326rpx 158rpx 202rpx;
      .text-wrapper_12 {
        background: url(https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng9bc42d55b7b42d17659011382bf812fc36e70c9e2f9274e1b78733992354841c)
          100% no-repeat;
        background-size: 100% 100%;
        .text_23 {
          width: 256rpx;
          overflow-wrap: break-word;
          color: rgba(255, 255, 255, 1);
          font-size: 34rpx;
          letter-spacing: -1.2000000476837158px;
          font-family: PingFangSC-Medium;
          font-weight: 500;
          text-align: right;
          white-space: nowrap;
          line-height: 48rpx;
          margin: 0 -30rpx 2rpx -4rpx;
        }
      }
    }
    .box_7 {
      background-color: rgba(255, 255, 255, 1);
      border-radius: 4px;
      position: relative;
      width: 714rpx;
      align-self: center;
      margin-top: 312rpx;
      padding: 22rpx 36rpx 18rpx 32rpx;
      .section_8 {
        position: relative;
        margin: 0 438rpx 0 4rpx;
        padding: 22rpx 68rpx 6rpx 56rpx;
        .group_3 {
          background-color: rgba(165, 229, 215, 1);
          border-radius: 5px;
          width: 80rpx;
          height: 20rpx;
        }
        .text_24 {
          position: absolute;
          left: 0;
          top: 0;
          overflow-wrap: break-word;
          color: rgba(51, 51, 51, 1);
          font-size: 34rpx;
          font-family: PingFangSC-Semibold;
          font-weight: 600;
          text-align: left;
          white-space: nowrap;
          line-height: 48rpx;
        }
      }
      .section_9 {
        width: 642rpx;
        align-self: center;
        margin-top: 40rpx;
        .image-text_7 {
          width: 316rpx;
          margin: 4rpx 0 6rpx 0;
          .group_4 {
            border-radius: 3px;
            background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/2c7f2944ae254f1795903d7af0883888_mergeImage.png);
            width: 88rpx;
            height: 88rpx;
          }
          .text-group_7 {
            margin: 2rpx 0 4rpx 0;
            .text_25 {
              overflow-wrap: break-word;
              color: rgba(51, 51, 51, 1);
              font-size: 28rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 40rpx;
              margin: 0 102rpx 0 2rpx;
            }
            .text_26 {
              overflow-wrap: break-word;
              color: rgba(102, 102, 102, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
              margin-top: 8rpx;
            }
          }
        }
        .section_3 {
          background-color: rgba(255, 255, 255, 1);
          padding: 0 4rpx 0 54rpx;
          .text-wrapper_3 {
            width: 150rpx;
            height: 34rpx;
            overflow-wrap: break-word;
            font-size: 0;
            font-family: PingFangSC-Medium;
            font-weight: 500;
            text-align: right;
            white-space: nowrap;
            line-height: 34rpx;
            margin-right: 4rpx;
            .text_5 {
              overflow-wrap: break-word;
              color: rgba(255, 88, 94, 1);
              font-size: 24rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
            .text_6 {
              overflow-wrap: break-word;
              color: rgba(153, 153, 153, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
            .text_7 {
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
            background-color: rgba(80, 186, 174, 1);
            border-radius: 13px;
            margin: 14rpx 0 0 26rpx;
            padding: 8rpx 28rpx 8rpx 28rpx;
            .text_8 {
              overflow-wrap: break-word;
              color: rgba(255, 255, 255, 1);
              font-size: 24rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: right;
              white-space: nowrap;
              line-height: 34rpx;
            }
          }
        }
      }
      .image_4 {
        width: 640rpx;
        height: 4rpx;
        margin: 40rpx 6rpx 0 0;
      }
      .section_10 {
        width: 642rpx;
        align-self: center;
        margin-top: 40rpx;
        .image-text_8 {
          width: 388rpx;
          margin: 2rpx 0 8rpx 0;
          .group_5 {
            border-radius: 3px;
            background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/8ddcc878d0094496a63fdce784f773d5_mergeImage.png);
            width: 88rpx;
            height: 88rpx;
          }
          .text-group_8 {
            margin: 2rpx 0 4rpx 0;
            .text_27 {
              overflow-wrap: break-word;
              color: rgba(51, 51, 51, 1);
              font-size: 28rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 40rpx;
              margin: 0 174rpx 0 2rpx;
            }
            .text_28 {
              overflow-wrap: break-word;
              color: rgba(102, 102, 102, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
              margin-top: 8rpx;
            }
          }
        }
        .section_4 {
          background-color: rgba(255, 255, 255, 1);
          padding: 0 4rpx 0 54rpx;
          .text-wrapper_5 {
            width: 150rpx;
            height: 34rpx;
            overflow-wrap: break-word;
            font-size: 0;
            font-family: PingFangSC-Medium;
            font-weight: 500;
            text-align: right;
            white-space: nowrap;
            line-height: 34rpx;
            margin-right: 4rpx;
            .text_9 {
              overflow-wrap: break-word;
              color: rgba(255, 88, 94, 1);
              font-size: 24rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
            .text_10 {
              overflow-wrap: break-word;
              color: rgba(153, 153, 153, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
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
          .text-wrapper_6 {
            background-color: rgba(80, 186, 174, 1);
            border-radius: 13px;
            margin: 14rpx 0 0 26rpx;
            padding: 8rpx 28rpx 8rpx 28rpx;
            .text_12 {
              overflow-wrap: break-word;
              color: rgba(255, 255, 255, 1);
              font-size: 24rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: right;
              white-space: nowrap;
              line-height: 34rpx;
            }
          }
        }
      }
      .image_5 {
        width: 640rpx;
        height: 4rpx;
        margin: 38rpx 6rpx 0 0;
      }
      .section_11 {
        width: 644rpx;
        margin: 42rpx 0 0 2rpx;
        .image-text_9 {
          width: 376rpx;
          margin: 2rpx 0 8rpx 0;
          .group_6 {
            border-radius: 3px;
            background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/a8b96f55563e45559c93d4a8502634f7_mergeImage.png);
            width: 88rpx;
            height: 88rpx;
          }
          .text-group_9 {
            margin: 2rpx 0 4rpx 0;
            .text_29 {
              overflow-wrap: break-word;
              color: rgba(51, 51, 51, 1);
              font-size: 28rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 40rpx;
              margin: 0 162rpx 0 2rpx;
            }
            .text_30 {
              overflow-wrap: break-word;
              color: rgba(102, 102, 102, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
              margin-top: 8rpx;
            }
          }
        }
        .section_5 {
          background-color: rgba(255, 255, 255, 1);
          padding: 0 4rpx 0 64rpx;
          .text-wrapper_7 {
            width: 140rpx;
            height: 34rpx;
            overflow-wrap: break-word;
            font-size: 0;
            font-family: PingFangSC-Medium;
            font-weight: 500;
            text-align: center;
            white-space: nowrap;
            line-height: 34rpx;
            margin-right: 4rpx;
            .text_13 {
              overflow-wrap: break-word;
              color: rgba(255, 88, 94, 1);
              font-size: 24rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
            .text_14 {
              overflow-wrap: break-word;
              color: rgba(153, 153, 153, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
            .text_15 {
              overflow-wrap: break-word;
              color: rgba(51, 51, 51, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
            }
          }
          .text-wrapper_8 {
            background-color: rgba(80, 186, 174, 1);
            border-radius: 13px;
            margin: 14rpx 0 0 16rpx;
            padding: 8rpx 28rpx 8rpx 28rpx;
            .text_16 {
              overflow-wrap: break-word;
              color: rgba(255, 255, 255, 1);
              font-size: 24rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: right;
              white-space: nowrap;
              line-height: 34rpx;
            }
          }
        }
      }
      .image_6 {
        width: 640rpx;
        height: 4rpx;
        margin: 38rpx 6rpx 0 0;
      }
      .section_12 {
        position: relative;
        width: 642rpx;
        align-self: center;
        margin-top: 42rpx;
        padding: 2rpx 0 0 102rpx;
        .image-text_10 {
          width: 540rpx;
          .text-group_10 {
            margin-bottom: 16rpx;
            .text_31 {
              overflow-wrap: break-word;
              color: rgba(51, 51, 51, 1);
              font-size: 28rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 40rpx;
              margin-right: 176rpx;
            }
            .text_32 {
              overflow-wrap: break-word;
              color: rgba(102, 102, 102, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
              margin-top: 8rpx;
            }
          }
          .section_6 {
            background-color: rgba(255, 255, 255, 1);
            padding: 0 4rpx 0 76rpx;
            .text-wrapper_9 {
              width: 156rpx;
              height: 34rpx;
              overflow-wrap: break-word;
              font-size: 0;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: right;
              white-space: nowrap;
              line-height: 34rpx;
              .text_17 {
                overflow-wrap: break-word;
                color: rgba(255, 88, 94, 1);
                font-size: 24rpx;
                font-family: PingFangSC-Medium;
                font-weight: 500;
                text-align: left;
                white-space: nowrap;
                line-height: 34rpx;
              }
              .text_18 {
                overflow-wrap: break-word;
                color: rgba(153, 153, 153, 1);
                font-size: 24rpx;
                font-weight: normal;
                text-align: left;
                white-space: nowrap;
                line-height: 34rpx;
              }
              .text_19 {
                overflow-wrap: break-word;
                color: rgba(51, 51, 51, 1);
                font-size: 24rpx;
                font-weight: normal;
                text-align: left;
                white-space: nowrap;
                line-height: 34rpx;
              }
            }
            .text-wrapper_10 {
              background-color: rgba(80, 186, 174, 1);
              border-radius: 13px;
              margin: 14rpx 0 0 28rpx;
              padding: 8rpx 28rpx 8rpx 28rpx;
              .text_20 {
                overflow-wrap: break-word;
                color: rgba(255, 255, 255, 1);
                font-size: 24rpx;
                font-family: PingFangSC-Medium;
                font-weight: 500;
                text-align: right;
                white-space: nowrap;
                line-height: 34rpx;
              }
            }
          }
        }
        .image-text_11 {
          position: absolute;
          left: 0;
          top: 0;
          width: 390rpx;
          height: 88rpx;
          .section_7 {
            border-radius: 3px;
            background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/9c69914c1ebb42b1a28c3d0ca593ec8d_mergeImage.png);
            width: 88rpx;
            height: 88rpx;
          }
          .text-group_11 {
            margin: 2rpx 0 4rpx 0;
            .text_31 {
              overflow-wrap: break-word;
              color: rgba(51, 51, 51, 1);
              font-size: 28rpx;
              font-family: PingFangSC-Medium;
              font-weight: 500;
              text-align: left;
              white-space: nowrap;
              line-height: 40rpx;
              margin-right: 176rpx;
            }
            .text_32 {
              overflow-wrap: break-word;
              color: rgba(102, 102, 102, 1);
              font-size: 24rpx;
              font-weight: normal;
              text-align: left;
              white-space: nowrap;
              line-height: 34rpx;
              margin-top: 8rpx;
            }
          }
        }
      }
      .image_10 {
        width: 268rpx;
        height: 10rpx;
        margin: 12rpx 186rpx 0 192rpx;
      }
      .image-wrapper_1 {
        box-shadow: 0px 2px 10px 0px rgba(0, 0, 0, 0.12);
        background-color: rgba(255, 255, 255, 0.91);
        border-radius: 5px;
        height: 96rpx;
        width: 96rpx;
        position: absolute;
        left: 636rpx;
        top: 502rpx;
        padding: 16rpx 16rpx 16rpx 16rpx;
        .label_1 {
          width: 64rpx;
          height: 64rpx;
        }
      }
    }
    .box_13 {
      background-color: rgba(255, 255, 255, 1);
      border-radius: 6px;
      position: absolute;
      left: 18rpx;
      top: 180rpx;
      width: 714rpx;
      height: 446rpx;
      padding-top: 28rpx;
      .text-wrapper_13 {
        background-color: rgba(82, 183, 175, 1);
        border-radius: 3px;
        margin: 0 418rpx 0 184rpx;
        padding: 0 10rpx 2rpx 6rpx;
        .text_33 {
          overflow-wrap: break-word;
          color: rgba(255, 255, 255, 1);
          font-size: 24rpx;
          font-weight: normal;
          text-align: left;
          white-space: nowrap;
          line-height: 34rpx;
        }
      }
      .image-text_12 {
        width: 380rpx;
        margin: 40rpx 300rpx 0 34rpx;
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
      .image_8 {
        width: 652rpx;
        height: 2rpx;
        margin: 30rpx 28rpx 0 34rpx;
      }
      .text_34 {
        width: 652rpx;
        height: 160rpx;
        overflow-wrap: break-word;
        color: rgba(51, 51, 51, 1);
        font-size: 28rpx;
        font-weight: normal;
        text-align: left;
        line-height: 40rpx;
        margin: 22rpx 28rpx 0 34rpx;
      }
      .group_7 {
        background-color: rgba(255, 255, 255, 1);
        border-radius: 6px;
        margin-top: -2rpx;
        padding: 24rpx 134rpx 38rpx 290rpx;
        .text_35 {
          overflow-wrap: break-word;
          color: rgba(82, 183, 175, 1);
          font-size: 24rpx;
          font-weight: normal;
          text-align: left;
          white-space: nowrap;
          line-height: 34rpx;
        }
        .thumbnail_7 {
          width: 20rpx;
          height: 10rpx;
          margin: 12rpx 0 12rpx 14rpx;
        }
        .thumbnail_8 {
          width: 20rpx;
          height: 10rpx;
          margin: 12rpx 0 12rpx 140rpx;
        }
      }
      .group_8 {
        border-radius: 6px;
        background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/6750185144ad44a58da3e2c018f99b3e_mergeImage.png);
        position: absolute;
        left: 32rpx;
        top: -68rpx;
        width: 132rpx;
        height: 144rpx;
      }
    }
  }
}

</style>
