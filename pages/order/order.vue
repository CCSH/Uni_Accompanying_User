<template>
	<view></view>
</template>
<script>
export default {
	data() {
		return {}
	},
	onLoad() {},
	methods: {
		isLogin() {
			let userInfo = uni.getStorageSync('userInfo')
			if (!userInfo) {
				uni.showToast({
					title: '用户未登录',
					icon: 'none',
					duration: 1000,
				})
				setTimeout(() => {
					uni.navigateTo({ url: '/pagesA/pages/login/login' })
				}, 1000)
				return false
			}
			return true
		},
	},
	onShow() {
		if (!this.isLogin()) {
			return
		}
	},
}
</script>
<style scoped lang="scss"></style>
