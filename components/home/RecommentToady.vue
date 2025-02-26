<template>
	<view class="recomment_today shadow">
		<div class="cover">
			<img :src="hotalInfo.imgSrc" alt="recomment_today" loading="lazy" />
		</div>
		<view class="recomment_info">
			<view class="hotal_info">
				<h2 class="hotal_name">{{hotalInfo.name}}</h2>
				<view class="hotal_mark">
					<i class="stars"></i>
					<span class="mark">{{hotalInfo.mark}}</span>
				</view>
			</view>
			<p class="distance">{{formattedDistance}}</p>
			<view class="hotal_types">
				<span class="type" v-for="(type, index) in hotalInfo.types" :key="index">{{ type }}</span>
			</view>
		</view>
	</view>
</template>

<script setup lang="ts">
	import { ref, computed } from "vue";
	import { HotalInfo } from "@/types/hotal";

	const hotalInfo = ref<HotalInfo>({
		imgSrc: "https://public.readdy.ai/ai/img_res/26c51c5e979530f4ca22d51a8f74dd6a.jpg",
		name: "米其林三星·望湘园",
		mark: 4.9,
		distance: 1200,
		types: ["创意湘菜", "会客宴请"]
	});

	const formattedDistance = computed(() => {
		if (hotalInfo.value.distance >= 1000) {
			return `${(hotalInfo.value.distance / 1000).toFixed(1)} km`;
		} else {
			return `${hotalInfo.value.distance} m`;
		}
	});
</script>

<style lang="scss" scoped>
	.recomment_today {
		width: 680rpx;
		background-color: #fff;
		border-radius: 40rpx;
		overflow: hidden;

		.recomment_info {
			padding: 0 20rpx;

			.hotal_info {
				display: flex;
				align-items: center;
				justify-content: space-between;
				line-height: 1;

				.hotal_name {
					font-size: 32rpx;
				}
			}

			.distance {
				color: #505864;
				margin: 10rpx 0;
			}

			.hotal_types {
				display: flex;
				align-items: center;
				justify-content: start;
				margin: 10rpx 0 25rpx 0;

				.type {
					padding: 8rpx 20rpx;
					font-size: 22rpx;
					font-weight: 700;
					background-color: #FDF1F0;
					border-radius: 50rpx;
					color: #ED7470;
					margin-right: 15rpx;
				}
			}
		}

		.cover {
			width: 100%;
			height: 400rpx;

			img {
				width: 100%;
			}
		}
	}
</style>