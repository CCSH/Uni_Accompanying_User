<template>
	<view class="page flex-col">
		<view class="box_1 flex-col">
			<view class="box_4 flex-col">
				<view class="box_5 flex-col">
					<view class="block_1 flex-row">
						<view class="text-wrapper_3 flex-col">
							<text class="text_6">1</text>
						</view>
						<image class="image_4" referrerpolicy="no-referrer" src="/static/point_line.png" />
						<view class="text-wrapper_4 flex-col">
							<text class="text_7">2</text>
						</view>
						<image class="image_5" referrerpolicy="no-referrer" src="/static/point_line.png" />
						<view class="text-wrapper_5 flex-col">
							<text class="text_8">3</text>
						</view>
						<image class="image_6" referrerpolicy="no-referrer" src="/static/point_line.png" />
						<view class="text-wrapper_6 flex-col">
							<text class="text_9">4</text>
						</view>
					</view>
					<view class="text-wrapper_7 flex-row justify-between">
						<text class="text_10">填写订单</text>
						<text class="text_11">在线支付</text>
						<text class="text_12">服务中</text>
						<text class="text_13">服务完成</text>
					</view>
				</view>
				<view class="box_6 flex-row" @click="$refs.popup_hospital.open()">
					<view class="group_4 flex-col"></view>
					<text class="text_14">检查预约</text>
					<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/more_lv@2x.png" />
					<text class="text_15">服务项目</text>
				</view>
			</view>
			<view class="box_7 flex-col">
				<view class="group_5 flex-row">
					<view class="group_6 flex-col"></view>
					<text class="text_16">服务项目</text>
				</view>
				<view class="group_7 flex-row">
					<text class="paragraph_1">
						就诊医院
						<br />
						就诊科室
						<br />
						就诊时间
					</text>
					<view class="text-wrapper_8 flex-col">
						<text class="paragraph_2" @click="$refs.popup_yiyuan.open()">
							成都416医院
							<br />
						</text>
						<text class="paragraph_3" @click="$refs.popup_department.open()">
							请选择就诊室
							<br />
						</text>
						<uni-datetime-picker class="paragraph_3" v-model="single"><view style="font-size: 28rpx; color: #999999">请选择就诊时间</view></uni-datetime-picker>
					</view>
					<view class="image-wrapper_1 flex-col">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
						<image class="thumbnail_8" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
						<image class="thumbnail_9" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
					</view>
				</view>
				<image class="image_7" referrerpolicy="no-referrer" />
				<image class="image_8" referrerpolicy="no-referrer" />
			</view>
			<view class="box_9 flex-col">
				<view class="box_10 flex-col">
					<view class="box_11 flex-row">
						<view class="group_9 flex-col"></view>
						<text class="text_22">就诊信息</text>
					</view>
					<view class="box_12 flex-row">
						<text class="text_23">就诊人</text>
						<text class="text_24" @click="$refs.popup_patient.open()">请选择就诊人</text>
						<image class="thumbnail_10" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
					</view>
					<view class="box_12 flex-row">
						<text class="text_23">优惠券</text>
						<text class="text_24" @click="$refs.popup_favorable.open()">请选择优惠券</text>
						<image class="thumbnail_10" referrerpolicy="no-referrer" src="/static/more_hui@2x.png" />
					</view>
				</view>
				<text class="text_25">注意事项</text>
				<text class="paragraph_4">
					1.仅支持当地医院的服务。
					<br />
					2.下单成功后，因个人原因，就诊时间前12小时内取消订单-扣除5%服务费用，就诊时间前6小时内取消订单-扣除10%服务费用，就诊时间前3小时内取消订单-扣除50%服务费用，就诊时间前2小时内取消订单-扣除100%服务费用。
				</text>
				<view class="image-text_1 flex-row justify-between">
					<image class="box_13 flex-col" :src="isAgreement ? '/static/fangkuai_h@2x.png' : '/static/fangkuai_n@2x.png'" mode="scaleToFill" @click="isAgreement = !isAgreement" />
					<view class="text-group_1 flex-col">
						<text class="text_26">我已认真阅读并同意预约相关</text>
						<text class="text_27" @click="showAgreement">《服务条款同意书》</text>
					</view>
				</view>
			</view>
			<view class="box_8 flex-col">
				<view class="group_8 flex-row">
					<text class="text_17">共计</text>
					<view class="text-wrapper_9">
						<text class="text_18">￥</text>
						<text class="text_19">148</text>
						<text class="text_20">.00</text>
					</view>
					<view class="text-wrapper_10 flex-col" @click="handlePlay">
						<text class="text_21">立即下单</text>
					</view>
				</view>
				<view class="image-wrapper_2 flex-row"></view>
			</view>
		</view>

		<!-- 悬浮 -->
		<drag-button :isDock="true" :existTabBar="true"></drag-button>
		<!-- 弹窗 -->
		<!-- 服务 -->
		<uni-popup ref="popup_hospital" type="bottom" :safe-area="false">
			<view class="pop_content">
				<view class="box_1 flex-col">
					<view class="block_3 flex-row justify-between">
						<view class="box_2 flex-col"></view>
						<image class="thumbnail_1" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_hospital.close()" />
						<text class="text_1">服务项目</text>
					</view>
					<view class="block_4 flex-row" @click="serveIndex = 0">
						<image :src="serveIndex == 0 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_1 flex-row justify-between">
							<view class="box_4 flex-col"></view>
							<view class="text-group_1 flex-col">
								<text class="text_2">全程陪诊</text>
								<text class="text_3">全程陪同服务，手续代办服务</text>
							</view>
						</view>
						<view class="image-text_2 flex-col">
							<image class="thumbnail_2" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_2">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_5 flex-row" @click="serveIndex = 1">
						<image :src="serveIndex == 1 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_3 flex-row justify-between">
							<view class="box_5 flex-col"></view>
							<view class="text-group_3 flex-col">
								<text class="text_4">代办买药</text>
								<text class="text_5">人工排队代买药服务</text>
							</view>
						</view>
						<view class="image-text_4 flex-col">
							<image class="thumbnail_4" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_4">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_6 flex-row" @click="serveIndex = 2">
						<image :src="serveIndex == 2 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_5 flex-row justify-between">
							<view class="group_1 flex-col"></view>
							<view class="text-group_5 flex-col">
								<text class="text_6">代办问诊</text>
								<text class="text_7">代客户到机构咨询及代开检查单服务</text>
							</view>
						</view>
						<view class="image-text_6 flex-col">
							<image class="thumbnail_5" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_6">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_7 flex-row" @click="serveIndex = 3">
						<image :src="serveIndex == 3 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_7 flex-row justify-between">
							<view class="block_9 flex-col"></view>
							<view class="text-group_7 flex-col">
								<text class="text_8">送取结果</text>
								<text class="text_9">送/取结果快递到家服务，服务仅限当…</text>
							</view>
						</view>
						<view class="image-text_8 flex-col">
							<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_8">详情</text>
						</view>
					</view>
					<image class="image_2" referrerpolicy="no-referrer" src="" />
					<view class="block_10 flex-row" @click="serveIndex = 4">
						<image :src="serveIndex == 4 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_3 flex-col" />
						<view class="image-text_9 flex-row justify-between">
							<view class="section_2 flex-col"></view>
							<view class="text-group_9 flex-col">
								<text class="text_10">尊享服务</text>
								<text class="text_11">组合套餐项目升级包</text>
							</view>
						</view>
						<view class="image-text_10 flex-col">
							<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/xiangqing@2x.png" />
							<text class="text-group_10">详情</text>
						</view>
					</view>
					<!-- <image class="image_2" referrerpolicy="no-referrer" src="" /> -->
				</view>
			</view>
		</uni-popup>
		<!-- 优惠券 -->
		<uni-popup ref="popup_favorable" type="bottom" :safe-area="false" borderRadius="38rpx   38rpx   0rpx   0rpx">
			<view class="popup_favorable">
				<view class="box_1 flex-col">
					<view class="group_1 flex-row justify-between">
						<view class="section_3 flex-col"></view>
						<image class="thumbnail_1" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_favorable.close()" />
						<text class="text_1">选择优惠券</text>
					</view>
					<view class="group_2 flex-row" @click="favorableIndex = 0">
						<view class="text-group_1 flex-col">
							<text class="text_2">陪诊优惠券</text>
							<text class="text_3">有效期至2024.06.06</text>
						</view>
						<view class="text-group_2 flex-col">
							<view class="text-wrapper_1">
								<text class="text_4">￥</text>
								<text class="text_5">100</text>
							</view>
							<text class="text_6">满800可用</text>
						</view>
						<image class="thumbnail_2" referrerpolicy="no-referrer" :src="favorableIndex == 0 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" />
					</view>
					<view class="group_2 flex-row" @click="favorableIndex = 1">
						<view class="text-group_1 flex-col">
							<text class="text_2">陪诊优惠券</text>
							<text class="text_3">有效期至2024.06.06</text>
						</view>
						<view class="text-group_2 flex-col">
							<view class="text-wrapper_1">
								<text class="text_4">￥</text>
								<text class="text_5">100</text>
							</view>
							<text class="text_6">满800可用</text>
						</view>
						<image class="thumbnail_2" referrerpolicy="no-referrer" :src="favorableIndex == 1 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" />
					</view>
					<view class="group_3 flex-row justify-between">
						<view class="box_2 flex-row justify-between">
							<text class="text_7">优惠</text>
							<view class="text-wrapper_2">
								<text class="text_8">￥</text>
								<text class="text_9">6</text>
							</view>
						</view>
						<text class="text_10" @click="$refs.popup_favorable.close()">确认</text>
					</view>
				</view>
			</view>
		</uni-popup>
		<!-- 就诊人 -->
		<uni-popup ref="popup_patient" type="bottom" :safe-area="false" class="popup_patient" background-color="#fff" borderRadius="38rpx   38rpx   0rpx   0rpx">
			<view class="block_2 flex-col">
				<view class="block_3 flex-row justify-between">
					<view class="box_3 flex-col"></view>
					<image class="thumbnail_1" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_patient.close()" />
					<text class="text_1">选择就诊人</text>
				</view>
				<image class="image_1" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPnga75db33691073ee7b893a76ea8943e1b6ba032ff3f782cebe482fdbf4b1fb372" />
				<view
					class="block_4 flex-row"
					@click="
						patientIndex = 0
						$refs.popup_patient.close()
					">
					<view class="image-text_1 flex-row justify-between">
						<image :src="patientIndex == 0 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
						<view class="text-group_1 flex-col">
							<text class="text_2">赵洪莉</text>
							<text class="text_3">1306***********024</text>
						</view>
					</view>
					<view class="text-wrapper_1 flex-col">
						<text class="text_4">本人</text>
						<text class="text_5">193****95</text>
					</view>
					<image class="thumbnail_2" referrerpolicy="no-referrer" src="/static/bianji@2x.png" @click="gotoEdit" />
				</view>
				<view
					class="block_4 flex-row"
					@click="
						patientIndex = 1
						$refs.popup_patient.close()
					">
					<view class="image-text_1 flex-row justify-between">
						<image :src="patientIndex == 1 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
						<view class="text-group_1 flex-col">
							<text class="text_2">赵洪莉2</text>
							<text class="text_3">1306***********024</text>
						</view>
					</view>
					<view class="text-wrapper_1 flex-col">
						<text class="text_4">本人</text>
						<text class="text_5">193****95</text>
					</view>
					<image class="thumbnail_2" referrerpolicy="no-referrer" src="/static/bianji@2x.png" />
				</view>
				<view class="text-wrapper_2 flex-col">
					<text class="text_6">添加就诊人</text>
				</view>
			</view>
		</uni-popup>
		<!-- 选择科室 -->
		<uni-popup ref="popup_department" type="bottom" :safe-area="false" class="popup_department" background-color="#fff" borderRadius="38rpx   38rpx   0rpx   0rpx">
			<view class="box_1 flex-col">
				<view class="group_6 flex-row justify-between">
					<view class="group_7 flex-col"></view>
					<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_department.close()" />
					<text class="text_6">选择科室</text>
				</view>
				<view class="group_8 flex-row">
					<view class="image-text_1 flex-row justify-between">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/tishi@2x.png" />
						<text class="text-group_1">提示：若是您对就诊的科室存在疑问，可以向客服咨询~</text>
					</view>
				</view>
				<image class="image_4" referrerpolicy="no-referrer" />
				<view class="group_9 flex-row justify-between">
					<view class="box_2 flex-col">
						<view class="block_1 flex-col">
							<!-- <view class="box_3 flex-col"></view> -->
						</view>
						<text class="paragraph_1 flex-col">
							<text :class="patientLeft == 0 ? 'patient_h' : ''" @click="patientLeft = 0">骨科</text>
							<text :class="patientLeft == 1 ? 'patient_h' : ''" @click="patientLeft = 1">其它科室</text>
							<text :class="patientLeft == 2 ? 'patient_h' : ''" @click="patientLeft = 2">健康管理科</text>
							<text :class="patientLeft == 3 ? 'patient_h' : ''" @click="patientLeft = 3">内科</text>
							<text :class="patientLeft == 4 ? 'patient_h' : ''" @click="patientLeft = 4">眼科</text>
							<text :class="patientLeft == 5 ? 'patient_h' : ''" @click="patientLeft = 5">儿科</text>
							<text :class="patientLeft == 6 ? 'patient_h' : ''" @click="patientLeft = 6">皮肤性病科</text>
							<text :class="patientLeft == 7 ? 'patient_h' : ''" @click="patientLeft = 7">医技科</text>
							<text :class="patientLeft == 8 ? 'patient_h' : ''" @click="patientLeft = 8">肿瘤医学科</text>
							<text :class="patientLeft == 9 ? 'patient_h' : ''" @click="patientLeft = 9">重症医学科</text>
						</text>
					</view>
					<text class="paragraph_2">
						<text @click="$refs.popup_department.close()">肾内科</text>
						<br />
						<text @click="$refs.popup_department.close()">呼吸科</text>
						<br />
						<text @click="$refs.popup_department.close()">心血管内科</text>
						<br />
						<text @click="$refs.popup_department.close()">感染/传染科</text>
						<br />
						<text @click="$refs.popup_department.close()">发热门诊</text>
						<br />
						<text @click="$refs.popup_department.close()">消化内科</text>
						<br />
						<text @click="$refs.popup_department.close()">血液科</text>
						<br />
						<text @click="$refs.popup_department.close()">内分泌科</text>
						<br />
						<text @click="$refs.popup_department.close()">风湿免疫科</text>
						<br />
						<text @click="$refs.popup_department.close()">全科门诊</text>
					</text>
				</view>
				<image class="image_5" referrerpolicy="no-referrer" src="https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng5a55bce0e61824e6b35e82f487c8fc2828194ab82d71f586b93de2f8b36bc031" />
			</view>
		</uni-popup>
		<!-- 选择医院 -->
		<uni-popup ref="popup_yiyuan" type="bottom" :safe-area="false" class="popup_yiyuan" background-color="#fff" borderRadius="38rpx   38rpx   0rpx   0rpx">
			<view class="box_3 flex-col">
				<view class="group_1 flex-row justify-between">
					<view class="section_1 flex-col"></view>
					<image class="thumbnail_1" referrerpolicy="no-referrer" src="/static/guanbi@2x.png" @click="$refs.popup_yiyuan.close()" />
					<text class="text_1">就诊医院</text>
				</view>
				<view class="group_2 flex-row">
					<view class="image-text_1 flex-row justify-between">
						<image class="thumbnail_2" referrerpolicy="no-referrer" src="/static/sousuo@2x.png" mode="aspectFit" />
						<input class="text-group_1" placeholder="请输入医院名称" />
					</view>
				</view>
				<view
					class="group_3 flex-row justify-between"
					@click="
						yiyuanIndex = 0
						$refs.popup_yiyuan.close()
					">
					<image :src="yiyuanIndex == 0 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
					<view class="image-text_2 flex-row justify-between">
						<image class="thumbnail_3" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_2">成都市新津区龙蟠路509路</text>
					</view>
					<view class="image-text_3 flex-row justify-between">
						<view class="group_4 flex-col"></view>
						<text class="text-group_3">四川省骨科医院（天府院区）</text>
					</view>
				</view>
				<image class="image_1" referrerpolicy="no-referrer" src="" />
				<view
					class="group_5 flex-row justify-between"
					@click="
						yiyuanIndex = 1
						$refs.popup_yiyuan.close()
					">
					<image :src="yiyuanIndex == 1 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
					<view class="image-text_4 flex-row justify-between">
						<image class="thumbnail_5" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_4">成都市武侯区一环路西一段132号</text>
					</view>
					<view class="image-text_5 flex-row justify-between">
						<view class="group_6 flex-col"></view>
						<text class="text-group_5">四川省骨科医院</text>
					</view>
				</view>
				<image class="image_2" referrerpolicy="no-referrer" src="" />
				<view
					class="group_7 flex-row justify-between"
					@click="
						yiyuanIndex = 2
						$refs.popup_yiyuan.close()
					">
					<image :src="yiyuanIndex == 2 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
					<view class="image-text_6 flex-row justify-between">
						<image class="thumbnail_6" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_6">成都市二环路北四段4号</text>
					</view>
					<view class="image-text_7 flex-row justify-between">
						<view class="box_5 flex-col"></view>
						<text class="text-group_7">成都416医院</text>
					</view>
				</view>
				<image class="image_3" referrerpolicy="no-referrer" src="" />
				<view
					class="group_9 flex-row justify-between"
					@click="
						yiyuanIndex = 3
						$refs.popup_yiyuan.close()
					">
					<image :src="yiyuanIndex == 3 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
					<view class="image-text_8 flex-row justify-between">
						<image class="thumbnail_7" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_8">成都市二环路北二段82号</text>
					</view>
					<view class="image-text_9 flex-row justify-between">
						<view class="group_10 flex-col"></view>
						<text class="text-group_9">成都大学附属医院</text>
					</view>
				</view>
				<image class="image_4" referrerpolicy="no-referrer" src="" />
				<view
					class="group_11 flex-row justify-between"
					@click="
						yiyuanIndex = 4
						$refs.popup_yiyuan.close()
					">
					<image :src="yiyuanIndex == 4 ? '/static/quan_h@2x.png' : '/static/quan_n@2x.png'" class="box_4 flex-col" />
					<view class="image-text_10 flex-row justify-between">
						<image class="thumbnail_8" referrerpolicy="no-referrer" src="/static/dingwei@2x.png" />
						<text class="text-group_10">四川省成都市蓉都大道天回路270号</text>
					</view>
					<view class="image-text_11 flex-row justify-between">
						<view class="box_7 flex-col"></view>
						<text class="text-group_11">成都军区总医院</text>
					</view>
				</view>
				<image class="image_5" referrerpolicy="no-referrer" src="" />
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
			isAgreement: true,
			serveIndex: 0,
			patientIndex: 0,
			patientLeft: 0,
			yiyuanIndex: 0,
			favorableIndex: 0,
			single: new Date(),
			constants: {},
		}
	},
	methods: {
		gotoEdit() {
			this.$refs.popup_patient.close()
			uni.navigateTo({
				url: '/pagesA/pages/add_client/add_client?edit=true',
			})
		},
		showAgreement() {
			uni.navigateTo({ url: '/pagesA/pages/privacy_agreement/privacy_agreement' })
		},
		showServe() {
			this.$refs.popup_serve.open()
		},
		handlePlay() {
			uni.showToast({
				title: '支付成功',
				icon: 'success',
				mask: true,
				duration: 1000,
			})
			setTimeout(() => {
				uni.reLaunch({ url: '/pages/home/home' })
			}, 1000)
		},
	},
}
</script>
<style scoped lang="scss">
.page {
	position: relative;
	width: 750rpx;
	overflow: auto;
	.box_1 {
		background-color: rgba(246, 246, 246, 1);
		position: relative;
		.group_2 {
			background-color: rgba(81, 187, 164, 1);
			padding: 32rpx 10rpx 20rpx 40rpx;
			.section_1 {
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
			.section_2 {
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
		.box_4 {
			padding: 24rpx 24rpx 22rpx 24rpx;
			.box_5 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				padding: 30rpx 24rpx 30rpx 22rpx;
				.block_1 {
					margin: 0 26rpx 0 30rpx;
					.text-wrapper_3 {
						background-color: rgba(81, 187, 164, 1);
						border-radius: 50%;
						padding: 6rpx 20rpx 6rpx 20rpx;
						.text_6 {
							overflow-wrap: break-word;
							color: rgba(255, 255, 255, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.image_4 {
						width: 42rpx;
						height: 2rpx;
						margin: 28rpx 0 22rpx 46rpx;
					}
					.text-wrapper_4 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin-left: 50rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_7 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.image_5 {
						width: 54rpx;
						height: 2rpx;
						margin: 28rpx 0 22rpx 46rpx;
					}
					.text-wrapper_5 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin-left: 26rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_8 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
					.image_6 {
						width: 54rpx;
						height: 2rpx;
						margin: 28rpx 0 22rpx 30rpx;
					}
					.text-wrapper_6 {
						background-color: rgba(241, 247, 247, 1);
						border-radius: 50%;
						margin-left: 44rpx;
						padding: 6rpx 16rpx 6rpx 18rpx;
						.text_9 {
							overflow-wrap: break-word;
							color: rgba(156, 165, 164, 1);
							font-size: 28rpx;
							font-weight: normal;
							text-align: left;
							white-space: nowrap;
							line-height: 40rpx;
						}
					}
				}
				.text-wrapper_7 {
					width: 656rpx;
					margin-top: 12rpx;
					.text_10 {
						overflow-wrap: break-word;
						color: rgba(81, 187, 164, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_12 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
					.text_13 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: right;
						white-space: nowrap;
						line-height: 40rpx;
					}
				}
			}
			.box_6 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				position: relative;
				margin-top: 28rpx;
				padding: 34rpx 32rpx 32rpx 50rpx;
				.group_4 {
					background-color: rgba(165, 229, 215, 1);
					border-radius: 5px;
					width: 80rpx;
					height: 20rpx;
					margin-top: 22rpx;
				}
				.text_14 {
					overflow-wrap: break-word;
					color: rgba(81, 187, 164, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-left: 398rpx;
				}
				.thumbnail_6 {
					width: 6rpx;
					height: 16rpx;
					margin: 12rpx 0 14rpx 24rpx;
				}
				.text_15 {
					position: absolute;
					left: 26rpx;
					top: 32rpx;
					overflow-wrap: break-word;
					color: rgba(69, 69, 69, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
		}
		.box_7 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 6px;
			align-self: center;
			margin-top: -2rpx;
			width: 702rpx;
			position: relative;
			padding: 32rpx 32rpx 14rpx 24rpx;
			.group_5 {
				position: relative;
				margin: 0 508rpx 0 2rpx;
				padding: 24rpx 32rpx 4rpx 24rpx;
				.group_6 {
					background-color: rgba(165, 229, 215, 1);
					border-radius: 5px;
					width: 80rpx;
					height: 20rpx;
				}
				.text_16 {
					position: absolute;
					left: 0;
					top: 0;
					overflow-wrap: break-word;
					color: rgba(69, 69, 69, 1);
					font-size: 34rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					white-space: nowrap;
					line-height: 48rpx;
				}
			}
			.group_7 {
				margin-top: 32rpx;
				.paragraph_1 {
					width: 112rpx;
					height: 324rpx;
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 108rpx;
				}
				.text-wrapper_8 {
					width: 196rpx;
					// height: 324rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-weight: normal;
					text-align: right;
					line-height: 108rpx;
					margin-left: 308rpx;
					.paragraph_2 {
						width: 196rpx;
						// height: 324rpx;
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 28rpx;
						font-weight: normal;
						// text-align: left;
						// line-height: 108rpx;
					}
					.paragraph_3 {
						position: relative;
						width: 196rpx;
						// height: 324rpx;
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						// text-align: left;
						// line-height: 108rpx;
					}
				}
				.image-wrapper_1 {
					margin: 44rpx 0 46rpx 24rpx;
					.thumbnail_7 {
						width: 6rpx;
						height: 16rpx;
					}
					.thumbnail_8 {
						width: 6rpx;
						height: 16rpx;
						margin-top: 94rpx;
					}
					.thumbnail_9 {
						width: 6rpx;
						height: 16rpx;
						margin-top: 92rpx;
					}
				}
			}
			.image_7 {
				position: absolute;
				left: 24rpx;
				top: 212rpx;
				width: 652rpx;
				height: 2rpx;
				background: #e7e7e7;
			}
			.image_8 {
				position: absolute;
				left: 24rpx;
				top: 328rpx;
				width: 652rpx;
				height: 2rpx;
				background: #e7e7e7;
			}
		}

		.box_9 {
			// position: absolute;
			// left: 0;
			// top: 790rpx;
			margin-bottom: 87rpx;
			width: 750rpx;
			height: 588rpx;
			padding: 22rpx 24rpx 16rpx 24rpx;
			.box_10 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 6px;
				padding: 26rpx 32rpx 6rpx 24rpx;
				.box_11 {
					position: relative;
					margin: 0 508rpx 0 2rpx;
					padding: 24rpx 32rpx 4rpx 24rpx;
					margin-bottom: 32rpx;
					.group_9 {
						background-color: rgba(165, 229, 215, 1);
						border-radius: 5px;
						width: 80rpx;
						height: 20rpx;
					}
					.text_22 {
						position: absolute;
						left: 0;
						top: 0;
						overflow-wrap: break-word;
						color: rgba(69, 69, 69, 1);
						font-size: 34rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 48rpx;
					}
				}
				.box_12 {
					//margin-top: 32rpx;
					.text_23 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						line-height: 108rpx;
					}
					.text_24 {
						overflow-wrap: break-word;
						color: rgba(153, 153, 153, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: center;
						line-height: 108rpx;
						margin-left: 364rpx;
					}
					.thumbnail_10 {
						width: 6rpx;
						height: 16rpx;
						margin: 44rpx 0 48rpx 24rpx;
					}
				}
			}
			.text_25 {
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 28rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: center;
				white-space: nowrap;
				line-height: 40rpx;
				margin: 24rpx 570rpx 0 20rpx;
			}
			.paragraph_4 {
				width: 650rpx;
				height: 170rpx;
				overflow-wrap: break-word;
				color: rgba(102, 102, 102, 1);
				font-size: 24rpx;
				font-weight: normal;
				text-align: left;
				line-height: 34rpx;
				margin: 6rpx 34rpx 0 18rpx;
			}
			.image-text_1 {
				width: 368rpx;
				margin: 20rpx 314rpx 0 20rpx;
				.box_13 {
					background-color: rgba(255, 255, 255, 1);
					// border-radius: 4px;
					width: 40rpx;
					height: 40rpx;
					// border: 1px solid rgba(153, 153, 153, 1);
					margin-bottom: 30rpx;
					background-size: cover;
				}
				.text-group_1 {
					.text_26 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_27 {
						overflow-wrap: break-word;
						color: rgba(80, 186, 174, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin: 2rpx 96rpx 0 0;
					}
				}
			}
			.image-wrapper_3 {
				box-shadow: 0px 2px 10px 0px rgba(0, 0, 0, 0.12);
				background-color: rgba(255, 255, 255, 0.91);
				border-radius: 5px;
				height: 96rpx;
				width: 96rpx;
				position: absolute;
				left: 654rpx;
				top: 290rpx;
				padding: 16rpx 16rpx 16rpx 16rpx;
				.label_1 {
					width: 64rpx;
					height: 64rpx;
				}
			}
			.thumbnail_11 {
				position: absolute;
				left: 44rpx;
				top: 562rpx;
				width: 40rpx;
				height: 40rpx;
			}
		}
		.box_8 {
			background-color: rgba(254, 254, 254, 1);
			width: 100vw;
			margin-top: 14rpx;
			padding: 10rpx 32rpx 18rpx 40rpx;
			.group_8 {
				.text_17 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 20rpx;
				}
				.text-wrapper_9 {
					width: 118rpx;
					height: 50rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: left;
					line-height: 34rpx;
					margin: 14rpx 0 12rpx 12rpx;
					.text_18 {
						height: 50rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 176, 1);
						font-size: 24rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						line-height: 34rpx;
					}
					.text_19 {
						height: 50rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 176, 1);
						font-size: 36rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
					}
					.text_20 {
						height: 50rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 176, 1);
						font-size: 24rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						line-height: 34rpx;
					}
				}
				.text-wrapper_10 {
					background-color: rgba(80, 186, 176, 1);
					border-radius: 19px;
					margin-left: 252rpx;
					padding: 22rpx 76rpx 20rpx 76rpx;
					.text_21 {
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
			.image-wrapper_2 {
				margin: 42rpx 208rpx 0 202rpx;
				.image_9 {
					width: 268rpx;
					height: 10rpx;
				}
			}
		}
	}
}

.pop_content {
	background: #fff;
	border-top-left-radius: 10px;
	border-top-right-radius: 10px;
	.box_1 {
		background-color: transparent;
		padding: 56rpx 32rpx 40rpx 30rpx;
		.block_3 {
			position: relative;
			width: 680rpx;
			margin-left: 8rpx;
			padding: 10rpx 0 4rpx 24rpx;
			.box_2 {
				background-color: rgba(165, 229, 215, 1);
				border-radius: 5px;
				width: 80rpx;
				height: 20rpx;
				margin-top: 14rpx;
			}
			.thumbnail_1 {
				width: 26rpx;
				height: 26rpx;
				// border: 1px solid rgba(153, 153, 153, 1);
				margin-bottom: 8rpx;
			}
			.text_1 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(69, 69, 69, 1);
				font-size: 34rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: left;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.box_3 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 50%;
			width: 36rpx;
			height: 36rpx;
			// border: 1px solid rgba(220, 220, 220, 1);
			margin: 26rpx 0 26rpx 0;
		}
		.block_4 {
			margin: 86rpx 4rpx 0 0;

			.image-text_1 {
				width: 414rpx;
				margin-left: 32rpx;
				.box_4 {
					border-radius: 3px;
					background-image: url(/static/quanchengpeizhen2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_1 {
					margin-top: 6rpx;
					.text_2 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-right: 200rpx;
					}
					.text_3 {
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
			.image-text_2 {
				margin: 10rpx 0 4rpx 154rpx;
				.thumbnail_2 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_2 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_1 {
			width: 616rpx;
			height: 4rpx;
			margin: 32rpx 6rpx 0 66rpx;
		}
		.block_5 {
			margin: 40rpx 4rpx 0 0;
			.thumbnail_3 {
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(77, 187, 177, 1);
				margin: 26rpx 0 26rpx 0;
			}
			.image-text_3 {
				width: 316rpx;
				margin-left: 32rpx;
				.box_5 {
					border-radius: 3px;
					background-image: url(/static/daibanmaiyao2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_3 {
					margin: 2rpx 0 8rpx 0;
					.text_4 {
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
					.text_5 {
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
			.image-text_4 {
				margin: 4rpx 0 10rpx 252rpx;
				.thumbnail_4 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_4 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_2 {
			width: 616rpx;
			height: 4rpx;
			margin: 26rpx 6rpx 0 66rpx;
			background: #e6e6e6;
		}
		.block_6 {
			margin: 38rpx 4rpx 0 0;
			.box_6 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin: 22rpx 0 30rpx 0;
			}
			.image-text_5 {
				width: 484rpx;
				margin-left: 32rpx;
				.group_1 {
					border-radius: 3px;
					background-image: url(/static/daibanwenzhen2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_5 {
					margin: 4rpx 0 6rpx 0;
					.text_6 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 0 270rpx 0 2rpx;
					}
					.text_7 {
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
			.image-text_6 {
				margin: 6rpx 0 8rpx 84rpx;
				.thumbnail_5 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_6 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_3 {
			width: 616rpx;
			height: 4rpx;
			margin: 32rpx 6rpx 0 66rpx;
		}
		.block_7 {
			margin: 30rpx 4rpx 0 0;
			.block_8 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin: 26rpx 0 26rpx 0;
			}
			.image-text_7 {
				width: 520rpx;
				margin-left: 32rpx;
				.block_9 {
					border-radius: 3px;
					background-image: url(/static/qusongjieguo@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_7 {
					margin-top: 8rpx;
					.text_8 {
						overflow-wrap: break-word;
						color: rgba(51, 51, 51, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Medium;
						font-weight: 500;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin: 0 306rpx 0 2rpx;
					}
					.text_9 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 6rpx;
					}
				}
			}
			.image-text_8 {
				margin: 12rpx 0 2rpx 48rpx;
				.thumbnail_6 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_8 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_4 {
			width: 616rpx;
			height: 4rpx;
			margin: 34rpx 6rpx 0 66rpx;
		}
		.block_10 {
			margin: 34rpx 4rpx 0 0;
			.group_2 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin: 26rpx 0 26rpx 0;
			}
			.image-text_9 {
				width: 316rpx;
				margin-left: 32rpx;
				.section_2 {
					border-radius: 3px;
					background-image: url(/static/xunxiangfuwu2@2x.png);
					width: 88rpx;
					height: 88rpx;
					background-size: cover;
				}
				.text-group_9 {
					margin: 4rpx 0 4rpx 0;
					.text_10 {
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
					.text_11 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 6rpx;
					}
				}
			}
			.image-text_10 {
				margin: 8rpx 0 6rpx 250rpx;
				.thumbnail_7 {
					width: 24rpx;
					height: 24rpx;
					align-self: center;
				}
				.text-group_10 {
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin-top: 16rpx;
				}
			}
		}
		.image_5 {
			width: 268rpx;
			height: 10rpx;
			align-self: center;
			margin-top: 90rpx;
		}
	}
}

.popup_favorable {
	.box_1 {
		background-color: #fff;
		border-radius: 20px 20px 0px 0px;
		padding: 44rpx 22rpx 100rpx 22rpx;
		.group_1 {
			position: relative;
			width: 674rpx;
			margin: 0 10rpx 0 22rpx;
			padding: 12rpx 0 2rpx 54rpx;
			.section_3 {
				background-color: rgba(165, 229, 215, 1);
				width: 80rpx;
				height: 20rpx;
				margin-top: 14rpx;
			}
			.thumbnail_1 {
				width: 24rpx;
				height: 24rpx;
				margin-bottom: 10rpx;
			}
			.text_1 {
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
		.group_2 {
			background-color: rgba(228, 244, 241, 0.3);
			border-radius: 5px;
			border: 1px solid rgba(80, 186, 174, 1);
			margin-top: 38rpx;
			padding: 38rpx 26rpx 36rpx 24rpx;
			.text-group_1 {
				margin-top: 6rpx;
				.text_2 {
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
				.text_3 {
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
			.text-group_2 {
				margin-left: 246rpx;
				.text-wrapper_1 {
					width: 100rpx;
					height: 60rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: right;
					line-height: 40rpx;
					align-self: center;
					.text_4 {
						height: 60rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 174, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						line-height: 40rpx;
					}
					.text_5 {
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
				.text_6 {
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
			.thumbnail_2 {
				width: 32rpx;
				height: 32rpx;
				margin: 32rpx 0 34rpx 34rpx;
			}
		}
		.group_3 {
			background-color: rgba(80, 186, 174, 1);
			border-radius: 22px;
			width: 706rpx;
			border: 1px solid rgba(80, 186, 174, 1);
			margin-top: 90rpx;
			padding-right: 64rpx;
			.box_2 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 22px 0px 0px 22px;
				width: 532rpx;
				border: 1px solid rgba(80, 186, 174, 1);
				padding: 8rpx 360rpx 16rpx 46rpx;
				.text_7 {
					overflow-wrap: break-word;
					color: rgba(80, 186, 174, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: right;
					white-space: nowrap;
					line-height: 40rpx;
					margin-top: 14rpx;
				}
				.text-wrapper_2 {
					width: 56rpx;
					// height: 60rpx;
					overflow-wrap: break-word;
					font-size: 0;
					font-family: PingFangSC-Semibold;
					font-weight: 600;
					text-align: right;
					line-height: 40rpx;
					margin-top: 8rpx;
					.text_8 {
						height: 60rpx;
						overflow-wrap: break-word;
						color: rgba(80, 186, 174, 1);
						font-size: 28rpx;
						font-family: PingFangSC-Semibold;
						font-weight: 600;
						text-align: left;
						line-height: 40rpx;
					}
					.text_9 {
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
			}
			.text_10 {
				overflow-wrap: break-word;
				color: rgba(255, 255, 255, 1);
				font-size: 28rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: right;
				white-space: nowrap;
				line-height: 40rpx;
				margin-top: 24rpx;
			}
		}
		.image_1 {
			width: 268rpx;
			height: 10rpx;
			align-self: center;
			margin-top: 42rpx;
		}
	}
}

.popup_patient {
	.block_2 {
		background: url(https://lanhu.oss-cn-beijing.aliyuncs.com/SketchPng6203202cec23b2c96f312596785bfae5b50899f78721ba965373f0ca380c9d37) 100% no-repeat;
		background-size: 100% 100%;
		padding: 58rpx 0 18rpx 0;
		.block_3 {
			position: relative;
			width: 680rpx;
			margin: 0 32rpx 0 38rpx;
			padding: 10rpx 0 4rpx 24rpx;
			.box_3 {
				background-color: rgba(165, 229, 215, 1);
				border-radius: 5px;
				width: 80rpx;
				height: 20rpx;
				margin-top: 14rpx;
			}
			.thumbnail_1 {
				width: 26rpx;
				height: 26rpx;
				// border: 1px solid rgba(153, 153, 153, 1);
				margin-bottom: 8rpx;
			}
			.text_1 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(69, 69, 69, 1);
				font-size: 34rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: left;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.image_1 {
			width: 750rpx;
			height: 2rpx;
			margin-top: 50rpx;
		}
		.block_4 {
			margin: 46rpx 36rpx 0 30rpx;
			.image-text_1 {
				width: 298rpx;
				.box_4 {
					background-color: rgba(255, 255, 255, 1);
					border-radius: 50%;
					width: 36rpx;
					height: 36rpx;
					// border: 1px solid rgba(220, 220, 220, 1);
					margin: 32rpx 0 32rpx 0;
				}
				.text-group_1 {
					.text_2 {
						overflow-wrap: break-word;
						color: rgba(69, 69, 69, 1);
						font-size: 28rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 40rpx;
						margin-right: 146rpx;
					}
					.text_3 {
						overflow-wrap: break-word;
						color: rgba(102, 102, 102, 1);
						font-size: 24rpx;
						font-weight: normal;
						text-align: left;
						white-space: nowrap;
						line-height: 34rpx;
						margin-top: 26rpx;
					}
				}
			}
			.text-wrapper_1 {
				margin-left: 2rpx;
				.text_4 {
					overflow-wrap: break-word;
					color: rgba(69, 69, 69, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
					margin-right: 106rpx;
				}
				.text_5 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
					margin: 26rpx 0 0 46rpx;
				}
			}
			.thumbnail_2 {
				width: 28rpx;
				height: 28rpx;
				margin: 34rpx 0 38rpx 194rpx;
			}
		}
		.text-wrapper_2 {
			background-color: rgba(80, 186, 174, 1);
			border-radius: 19px;
			align-self: center;
			margin-top: 580rpx;
			width: 690rpx;
			padding: 18rpx 274rpx 18rpx 276rpx;
			.text_6 {
				overflow-wrap: break-word;
				color: rgba(254, 254, 254, 1);
				font-size: 28rpx;
				font-family: PingFangSC-Medium;
				font-weight: 500;
				text-align: left;
				white-space: nowrap;
				line-height: 40rpx;
			}
		}
		.image_2 {
			width: 268rpx;
			height: 10rpx;
			align-self: center;
			margin-top: 44rpx;
		}
	}
}

.popup_department {
	position: relative;
	.box_1 {
		padding: 60rpx 0 18rpx 0;
		background: transparent;
		.group_6 {
			position: relative;
			width: 680rpx;
			margin: 0 32rpx 0 38rpx;
			padding: 10rpx 0 4rpx 24rpx;
			.group_7 {
				background-color: rgba(165, 229, 215, 1);
				border-radius: 5px;
				width: 80rpx;
				height: 20rpx;
				margin-top: 14rpx;
			}
			.thumbnail_6 {
				width: 26rpx;
				height: 26rpx;
				// border: 1px solid rgba(153, 153, 153, 1);
				margin-bottom: 8rpx;
			}
			.text_6 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(69, 69, 69, 1);
				font-size: 34rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: left;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.group_8 {
			background-color: rgba(228, 244, 241, 1);
			border-radius: 4px;
			margin: 32rpx 32rpx 0 38rpx;
			padding: 8rpx 32rpx 10rpx 20rpx;
			.image-text_1 {
				width: 628rpx;
				.thumbnail_7 {
					width: 16rpx;
					height: 20rpx;
					margin: 8rpx 0 6rpx 0;
				}
				.text-group_1 {
					overflow-wrap: break-word;
					color: rgba(81, 187, 164, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
		}
		.image_4 {
			width: 750rpx;
			height: 2rpx;
			margin-top: 30rpx;
			background: #e6e6e6;
		}
		.group_9 {
			width: 486rpx;
			margin-right: 264rpx;
			background: #fff;
			.box_2 {
				background-color: rgba(246, 246, 246, 1);
				position: relative;
				padding: 332rpx 0 698rpx 0;
				.block_1 {
					background-color: rgba(255, 255, 255, 1);
					padding-right: 292rpx;
					.box_3 {
						background-color: rgba(80, 186, 174, 1);
						width: 4rpx;
						height: 110rpx;
					}
				}
				.paragraph_1 {
					position: absolute;
					left: 0;
					top: 0;
					width: 100%;

					// height: 1100rpx;
					// overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 28rpx;
					font-weight: normal;
					text-align: left;
					line-height: 110rpx;
					text {
						padding-left: 30rpx;
						width: 100%;
						display: block;
					}
					.patient_h {
						border-left: 4rpx solid #50baae;
						background: #fff;
					}
				}
			}
			.paragraph_2 {
				width: 154rpx;
				height: 1100rpx;
				overflow-wrap: break-word;
				color: rgba(51, 51, 51, 1);
				font-size: 28rpx;
				font-weight: normal;
				text-align: left;
				line-height: 110rpx;
				text {
					width: 100%;
					display: block;
				}
			}
		}
		.image_5 {
			width: 268rpx;
			height: 10rpx;
			align-self: center;
			margin-top: 30rpx;
		}
	}
}

/deep/.uni-datetime-picker--btn {
	background: #50baae;
}
/deep/.uni-calendar-item--checked {
	background: #50baae !important;
}
/deep/.uni-datetime-picker-btn-text {
	color: #50baae !important;
}

.popup_yiyuan {
	.box_4 {
		background-color: rgba(255, 255, 255, 1);
		border-radius: 50%;
		width: 36rpx;
		height: 36rpx;
		border: 1px solid rgba(220, 220, 220, 1);
		margin-bottom: 28rpx;
	}
	.box_3 {
		background: transparent;
		padding: 62rpx 30rpx 18rpx 30rpx;
		.group_1 {
			position: relative;
			width: 680rpx;
			margin: 0 2rpx 0 8rpx;
			padding: 10rpx 0 4rpx 24rpx;
			.section_1 {
				background-color: rgba(165, 229, 215, 1);
				border-radius: 5px;
				width: 80rpx;
				height: 20rpx;
				margin-top: 14rpx;
			}
			.thumbnail_1 {
				width: 26rpx;
				height: 26rpx;
				// border: 1px solid rgba(153, 153, 153, 1);
				margin-bottom: 8rpx;
			}
			.text_1 {
				position: absolute;
				left: 0;
				top: 0;
				overflow-wrap: break-word;
				color: rgba(69, 69, 69, 1);
				font-size: 34rpx;
				font-family: PingFangSC-Semibold;
				font-weight: 600;
				text-align: left;
				white-space: nowrap;
				line-height: 48rpx;
			}
		}
		.group_2 {
			background-color: rgba(255, 255, 255, 1);
			border-radius: 4px;
			border: 1px solid rgba(230, 230, 230, 1);
			margin-top: 44rpx;
			padding: 18rpx 462rpx 14rpx 16rpx;
			.image-text_1 {
				width: 208rpx;
				.thumbnail_2 {
					width: 30rpx;
					height: 30rpx;
					margin: 2rpx 0 2rpx 0;
				}
				.text-group_1 {
					margin-left: 10rpx;
					overflow-wrap: break-word;
					color: rgba(153, 153, 153, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
		}
		.group_3 {
			position: relative;
			width: 530rpx;
			margin: 52rpx 160rpx 0 0;
			padding: 28rpx 52rpx 0 0;

			.image-text_2 {
				width: 312rpx;
				margin-top: 30rpx;
				.thumbnail_3 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_2 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_3 {
				position: absolute;
				left: 66rpx;
				top: 0;
				width: 464rpx;
				height: 86rpx;
				.group_4 {
					border-radius: 4px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/3e1a9f8b6cac489c9fe88f0b54761701_mergeImage.png);
					width: 80rpx;
					height: 80rpx;
					margin-top: 6rpx;
				}
				.text-group_3 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
		}
		.image_1 {
			width: 616rpx;
			height: 4rpx;
			margin: 40rpx 12rpx 0 62rpx;
			background: #e6e6e6;
		}
		.group_5 {
			position: relative;
			width: 546rpx;
			padding-top: 28rpx;
			margin: 36rpx 144rpx 0 0;
			.thumbnail_4 {
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(77, 187, 177, 1);
				margin-bottom: 28rpx;
			}
			.image-text_4 {
				width: 380rpx;
				margin-top: 30rpx;
				.thumbnail_5 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_4 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_5 {
				position: absolute;
				left: 66rpx;
				top: 0;
				width: 296rpx;
				height: 86rpx;
				.group_6 {
					border-radius: 4px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/4afef58c13274e229ba0d5aaa045d8d4_mergeImage.png);
					width: 80rpx;
					height: 80rpx;
					margin-top: 6rpx;
				}
				.text-group_5 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
		}
		.image_2 {
			width: 616rpx;
			height: 4rpx;
			margin: 42rpx 12rpx 0 62rpx;
			background: #e6e6e6;
		}
		.group_7 {
			position: relative;
			width: 448rpx;
			padding-top: 28rpx;
			margin: 36rpx 242rpx 0 0;
			.group_8 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin-bottom: 26rpx;
			}
			.image-text_6 {
				width: 284rpx;
				margin-top: 28rpx;
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
				left: 66rpx;
				top: 0;
				width: 256rpx;
				height: 86rpx;
				.box_5 {
					border-radius: 4px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/54db6ac71300460c88579a612017009d_mergeImage.png);
					width: 80rpx;
					height: 80rpx;
					margin-top: 6rpx;
				}
				.text-group_7 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
		}
		.image_3 {
			width: 616rpx;
			height: 4rpx;
			margin: 42rpx 12rpx 0 62rpx;
			background: #e6e6e6;
		}
		.group_9 {
			position: relative;
			width: 462rpx;
			padding-top: 28rpx;
			margin: 36rpx 228rpx 0 0;
			.section_2 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin-bottom: 26rpx;
			}
			.image-text_8 {
				width: 298rpx;
				margin-top: 28rpx;
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
				left: 66rpx;
				top: 0;
				width: 322rpx;
				height: 86rpx;
				.group_10 {
					border-radius: 4px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/e67db92637714f88a1c79bdf665f41ce_mergeImage.png);
					width: 80rpx;
					height: 80rpx;
					margin-top: 6rpx;
				}
				.text-group_9 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
		}
		.image_4 {
			width: 616rpx;
			height: 4rpx;
			margin: 44rpx 12rpx 0 62rpx;
			background: #e6e6e6;
		}
		.group_11 {
			position: relative;
			width: 570rpx;
			padding-top: 28rpx;
			margin: 34rpx 120rpx 0 0;
			.box_6 {
				background-color: rgba(255, 255, 255, 1);
				border-radius: 50%;
				width: 36rpx;
				height: 36rpx;
				border: 1px solid rgba(220, 220, 220, 1);
				margin-bottom: 26rpx;
			}
			.image-text_10 {
				width: 406rpx;
				margin-top: 28rpx;
				.thumbnail_8 {
					width: 22rpx;
					height: 28rpx;
					margin: 2rpx 0 4rpx 0;
				}
				.text-group_10 {
					overflow-wrap: break-word;
					color: rgba(102, 102, 102, 1);
					font-size: 24rpx;
					font-weight: normal;
					text-align: left;
					white-space: nowrap;
					line-height: 34rpx;
				}
			}
			.image-text_11 {
				position: absolute;
				left: 66rpx;
				top: 0;
				width: 294rpx;
				height: 86rpx;
				.box_7 {
					border-radius: 4px;
					background-image: url(https://lanhu-dds-backend.oss-cn-beijing.aliyuncs.com/merge_image/imgs/1086e7f7c5b2402aa7232a0f57c31ae5_mergeImage.png);
					width: 80rpx;
					height: 80rpx;
					margin-top: 6rpx;
				}
				.text-group_11 {
					overflow-wrap: break-word;
					color: rgba(51, 51, 51, 1);
					font-size: 28rpx;
					font-family: PingFangSC-Medium;
					font-weight: 500;
					text-align: left;
					white-space: nowrap;
					line-height: 40rpx;
				}
			}
		}
		.image_5 {
			width: 616rpx;
			height: 4rpx;
			margin: 44rpx 12rpx 0 62rpx;
			background: #e6e6e6;
		}
		.image_6 {
			width: 268rpx;
			height: 10rpx;
			align-self: center;
			margin-top: 68rpx;
		}
	}
}
</style>
