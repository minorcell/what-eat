<template>
	<view class="card shadow">
		<view class="cover">
			<img :src="props.hotalInfo.imgSrc" :alt="props.hotalInfo.name" />
		</view>
		<h3 class="name">{{props.hotalInfo.name}}</h3>
		<view class="mark">
			<i></i>
			<span>{{props.hotalInfo.mark}}</span>
		</view>
		<view class="info">
			<span class="distance">{{formattedDistance}}</span>
			<span style="margin: 0 5rpx;">|</span>
			<span class="price">人均¥{{props.hotalInfo.price}}</span>
		</view>
	</view>
</template>

<script setup lang="ts">
	import { computed } from "vue"
	import { HotalInfo } from '@/types/hotal';

	const props = defineProps<{
		hotalInfo : HotalInfo;
	}>();

	const formattedDistance = computed(() => {
		if (props.hotalInfo.distance >= 1000) {
			return `${(props.hotalInfo.distance / 1000).toFixed(1)} km`;
		} else {
			return `${props.hotalInfo.distance} m`;
		}
	});
</script>

<style scoped lang="scss">
	.card {
		width: 375rpx;
		display: flex;
		flex-direction: column;
		width: 100%;
		border-radius: 40rpx;
		background-color: #fff;
		overflow: hidden;

		.cover {
			width: 330rpx;
			height: 225rpx;
			overflow: hidden;
			display: flex;
			align-items: center;
			justify-content: center;

			img {
				width: 100%;
				height: auto;
			}
		}

		.name {
			margin: 20rpx 0 10rpx 20rpx;
			font-size: 30rpx;
		}

		.mark span {
			font-size: 28rpx;
			margin: 10rpx 0 10rpx 20rpx;
		}

		.info {
			color: #4D5562;
			font-size: 24rpx;
			margin: 10rpx 0 20rpx 20rpx;
		}
	}
</style>