<template>
	<view class="header">
		<view class="logo">
			<img src="../../static/logo.svg" alt="logo" />
		</view>
		<view class="tools">
			<img src="@/static/icon/search.svg" alt="search" />
			<img src="@/static/icon/setting.svg" alt="setting" />
		</view>
	</view>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
	.header {
		width: 750rpx;
		height: 110rpx;
		background-color: #fff;
		z-index: 100;
		position: fixed;
		top: 0;
		display: flex;
		justify-content: space-between;
		padding: 0 30rpx;
		box-shadow: 1rpx 1rpx 5rpx rgba(0, 0, 0, 0.1);

		.logo,
		.tools {
			height: 100%;
			display: flex;
			align-items: center;

			img {
				height: 40%;
			}
		}
		
		.tools {
			img {
				margin: 0 20rpx;
			}
			
			img:last-child {
				margin-right: 0;
			}
		}
	}
</style>