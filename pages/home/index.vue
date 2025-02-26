<template>
	<view class="container">
		<Header />
		<view class="title">
			<h1 class="recomment_title">今日首推</h1>
		</view>
		<RecommentToady />
		<view class="title">
			<h1 class="recomment_title recomment_others_title">其他推荐</h1>
		</view>
		<view class="recomment_others">
			<RecommentOther v-for="hotalInfo in hotalsInfo" :key="hotalInfo.name"
				:hotalInfo="hotalInfo"
			/>
		</view>
	</view>
</template>

<script lang="ts" setup>
	import Header from "../../components/common/Header.vue";
	import RecommentToady from "../../components/home/RecommentToady.vue";
	import RecommentOther from "../../components/home/RecommentOther.vue";
	import { HotalInfo } from "../../types/hotal";
	import {ref} from "vue"
	
	const hotalsInfo = ref<HotalInfo[]>([
		{
			imgSrc: "https://public.readdy.ai/ai/img_res/b5d5c48bbb9420f312f618ae092e83ad.jpg",
			name: "江南小馆",
			mark: 4.8,
			distance: 800,
			price: 199
		},
		{
			imgSrc: "https://public.readdy.ai/ai/img_res/88d2ddca436f945bee59ae621f83e1a5.jpg",
			name: "悦轩餐厅",
			mark: 4.7,
			distance: 1764,
			price: 268
		},
		{
			imgSrc: "https://public.readdy.ai/ai/img_res/3ae24aded6aa2ccb245ee76ca7e94f47.jpg",
			name: "山口寿司",
			mark: 3.9,
			distance: 2611,
			price: 98
		},
		{
			imgSrc: "https://public.readdy.ai/ai/img_res/63e8ebf36f0709aa8c587062d3eedf46.jpg",
			name: "罗马假日",
			mark: 5.0,
			distance: 8.2,
			price: 499
		}
	])
</script>

<style scoped lang="scss">
	.title {
		width: 100%;
		padding-left: 35rpx;
	}

	.recomment_title {
		margin: 25rpx 0 20rpx 0;
		font-size: 45rpx;
		float: left;
		line-height: 1.5;
	}

	.recomment_others_title {
		font-size: 35rpx;
	}
	
	.recomment_others {
		width: 680rpx;
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 20rpx;
		padding-bottom: 50rpx;
	}
</style>