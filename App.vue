<!-- <template>
	<div id="app">
		<router-view></router-view>
	</div>
</template> -->

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

<style lang="scss">
	/* 注意要写在第一行，同时给style标签加入lang="scss"属性 */
	@import "uview-ui/index.scss";

	/*每个页面公共css */
	/* #ifdef MP-WEIXIN */
	:not(not) {
		/* *所有选择器 */
		box-sizing: border-box;
	}

	/* #endif */

	@font-face {
		font-family: "iconfont";
		/* Project id 2528993 */
		src: url('./static/icon/common/iconfont/iconfont.woff2?t=1620288181130') format('woff2'),
			url('./static/icon/common/iconfont/iconfont.woff?t=1620288181130') format('woff'),
			url('./static/icon/common/iconfont/iconfont.ttf?t=1620288181130') format('truetype');
	}

	.iconfont {
		font-family: "iconfont" !important;
		font-size: 16px;
		font-style: normal;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}

	.icon-gouwuche:before {
		content: "\e632";
	}

	.icon-zhuangxiu:before {
		content: "\e675";
		color: green;
	}

	.icon-maimaiche:before {
		content: "\e638";
		color: #ff5500;
	}

	.icon-fangkeyaoqingmdpi:before {
		content: "\e614";
		color: #00aa7f;
	}

	.icon-huangguanguanjundiyihuiyuan:before {
		content: "\e61a";
	}

	.icon-xiaoxi:before {
		content: "\e691";
	}

	.icon-shui:before {
		content: "\e607";
		color: #55aaff;
	}

	.icon-qingli:before {
		content: "\e60d";
		color: #004e76;
	}

	.icon-baoxiu:before {
		content: "\e690";
		color: #004e76;
	}

	.icon-saoyisao:before {
		content: "\e6ea";
		color: #004e76;
	}

	.icon-kuaidichaxun:before {
		content: "\e61d";
		color: #ffaa00;
	}

	.icon-weixiu:before {
		content: "\e6da";
		color: orange;
	}

	.icon-_dayinxiaopiao:before {
		content: "\e82b";
		color: orange;
	}
	
	
	// aa
	.icon-lvyou:before {
	  content: "\e601";
	  color: #778beb;
	}
	
	.icon-qinggan:before {
	  content: "\e602";
	  color: #cf6a87;
	}
	
	.icon-yangsheng:before {
	  content: "\e603";
	}
	
	.icon-tiyu:before {
	  content: "\e604";
	  color: #cf6a87;
	}
	
	.icon-shenghuo:before {
	  content: "\e605";
	  color: #e15f41;
	}
	
	.icon-youxi:before {
	  content: "\e606";
	  color: #786fa6;
	}
	
	.icon-gaoxiao:before {
	  content: "\e607";
	}
	
	.icon-yuer:before {
	  content: "\e608";
	  color: #3dc1d3;
	}
	
	.icon-lishi:before {
	  content: "\e609";
	}
	
	.icon-yule:before {
	  content: "\e60a";
	}
	
	.icon-lieqi:before {
	  content: "\e60b";
	  color: #ea8685;
	}
	
	.icon-meishi:before {
	  content: "\e60c";
	  color: #f78fb3;
	}
	
	.icon-tianqi:before {
	  content: "\e60d";
	  color: #303952;
	}

</style>
