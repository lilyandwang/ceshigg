<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view id="banner_2_0">
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
				window.TencentGDT = window.TencentGDT || [];
				TencentGDT.push({
				app_id: '1111221443',
				placement_id: '7081947758088079', // 广告位id，请从联盟平台广告位获取
				type: 'native', // 广告类型
				display_type: 'banner', // 广告播放类型: banner广告
				carousel: 3000, // 轮播时间，> 3000数字类型，否则轮播会被取消
				containerid: 'banner_2_0', // 广告容器
				onComplete: function(res) {
					console.log('banner', res)
					if (res.ret == 0) {
						console.log('广告播放成功');
					} else {
						console.log('广告播放失败');
					}
				}
			});


			// H5 SDK接入全局只需运行一次
			(function() {
				var doc = document,
					h = doc.getElementsByTagName('head')[0],
					s = doc.createElement('script');
				s.async = true;
				s.src = '//qzs.qq.com/qzone/biz/res/i.js';
				h && h.insertBefore(s, h.firstChild);
			})();

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.banner_2_0{
		width: 100%;
	}
</style>
