<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
.container {
	background-color: #FAFAFA;
	min-height: 100vh;
	width: 750rpx;
	padding-top: 120rpx;
	display: flex;
	flex-direction: column;
	align-items: center;
}

* {
	box-sizing: border-box;
}

.shadow {
	box-shadow: 0rpx 5rpx 5rpx rgba(0, 0, 0, 0.1);
}
</style>
