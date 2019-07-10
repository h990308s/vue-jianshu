<style scoped>
	.bod {
		margin: 50px auto;
		width: 65%;
	}

	.body-left {
		height: 2000px;
		border: 1px solid red;
	}

	.layui-tab-brief>.layui-tab-title .layui-this {
		color: #646464;
		font-size: 15px;
	}

	.layui-tab-title li {
		font-weight: bold;
		color: #969696;
		font-size: 15px;
	}

	.layui-tab-brief>.layui-tab-more li.layui-this:after,
	.layui-tab-brief>.layui-tab-title .layui-this:after {
		border-bottom: 2px solid #646464;
	}

	.spa span {
		font-size: 12px;
		color: #ec6e56;
	}

	.cont1 img {
		width: 52px;
		height: 52px;
		border-radius: 4px;
	}

	.cont1 {
		margin-top: 15px;
	}

	.cont-1 a {
		font-size: 18px;
		font-weight: 700;
		color: #333;
		display: block;
		margin: 0 0 10px;
	}

	.cont-1 p {
		color: #969696;
		font-size: 12px;
		margin: 0 0 10px;
	}

	.cont-1 span {
		font-size: 12px;
		color: #969696;
	}

	.cont-r a {
		display: block;
		width: 100px;
		height: 40px;
		background-color: #42c02e;
		border-radius: 20px;
	}

	.cont-r {
		margin-top: 10px;
		padding-left: 10px;
	}

	.cont-r img {
		width: 125px;
		height: 100px;
		border-radius: 5px;
	}

	.cont-r a span {
		display: block;
		font-size: 16px;
		font-weight: 400;
		color: #FFFFFF;
		text-align: center;
		line-height: 40px;
	}

	.bod-bottom {
		width: 100%;
		height: 40px;
		margin: 30px auto 60px;
		padding: 10px 15px;
		text-align: center;
		font-size: 15px;
		border-radius: 20px;
		background-color: #a5a5a5;
		display: block;
	}

	.bod-bottom a {
		color: #FFFFFF;
	}

	.title-t img {
		width: 80px;
		height: 80px;
		border-radius: 5px;
	}

	.title-r a {
		font-size: 21px;
		font-weight: 700;
		margin-left: -15px;
	}

	.title-r p {
		color: #969696;
		font-size: 14px;
		margin: 15px 0 10px 0;
	}

	.cont-r1 a {
		display: block;
		width: 100px;
		height: 36px;
		border: 1px solid #42c02e;
		border-radius: 20px;
		cursor: pointer;
	}

	.cont-r1 {
		margin-top: 20px;
		margin-left: 60px;
	}

	.cont-r1 a span {
		display: block;
		font-size: 16px;
		font-weight: 400;
		color: #42c02e;
		text-align: center;
		line-height: 36px;
	}

	.seach-button {
		position: absolute;
		top: 8px;
		right: 6px;
		width: 50px;
		height: 30px;
		color: #969696;
		text-align: center;
	}

	.seach {
		padding: 0 0px 0 20px;
		width: 96%;
		height: 35px;
		font-size: 14px;
		background-color: hsla(0, 0%, 71%, .2);
		border: none;
		border-radius: 40px;
	}

	.notic {
		display: block;
		margin-top: 5px;
		font-size: 13px;
		vertical-align: middle;
		color: #969696;
	}

	.modal-header {
		padding: 20px;
		border-bottom: 1px solid #e5e5e5;
	}

	.modal-title {
		font-size: 17px;
		font-weight: 700;
		color: #333;
	}

	.father {
		width: 100%;
		height: 100%;
	}

	.mask {
		width: 100%;
		height: 100%;
		position: fixed;
		top: 0;
		left: 0;
		background: #000;
		opacity: 0.3;
		z-index: 999;
	}

	button {
		display: block;
		width: 100px;
		height: 40px;
		margin-top: 65%;
		margin-left: 41%;
		text-align: center;
		border-radius: 10px;
		background-color: #969696;
		border: none;
	}

	.child {
		position: fixed;
		width: 560px;
		height: 600px;
		border: 1px solid #ccc;
		top: 25px;
		left: 30%;
		background: #fff;
		border-radius: 20px;
		z-index: 999;
	}
</style>
<template>

	<div>
		<div class="mask" v-show="maskShow" @click="setMaskShow"></div>
		<div class="child" id="child" v-show="maskShow">
			<div class="modal-header">
				<h4 class="modal-title">给该专题投稿</h4>
				<span class="notic">每篇文章有总共有5次投稿机会</span>
				<div style="    margin: 20px 0 0;position: relative;">
					<input placeholder="搜索我的文章" type="text" class="seach">
					<a class="seach-button" href="">搜索</a>
				</div>
			</div>

			<button @click="setMaskShow">关闭</button>
		</div>
		<!-- 右边内容 -->
		<div class="layui-col-md9" style="padding-left: 35px;">
			<div class="layui-col-md12">
				<div class="layui-col-md2 title-t layui-hide-xs">
					<img src="../assets/12.webp" alt="">
				</div>
				<div class="layui-col-md5 title-r">
					<a href="">目标分大目标、小目标</a>
					<p><a style="color:#3194d0; font-size: 14px;" href="">简书</a>&nbsp;编 · 收录了152737篇文章 · 3061536人关注</p>
				</div>
				<div class="layui-col-md1 cont-r1 layui-hide-xs">
					<a @click="setMaskShow" style="width:62px;"><span>投稿</span></a>
				</div>
				<div class="layui-col-md1 cont-r1 layui-hide-xs" style="margin-left:25px;">
					<a href=""><span>专题主页&nbsp;></span></a>
				</div>


			</div>
		</div>
		<div class="layui-col-md9">

			<div class="layui-tab layui-tab-brief" lay-filter="docDemoTabBrief">
				<ul class="layui-tab-title">
					<li class="layui-this layui-icon layui-icon-list">最新收录</li>
					<li> <span class="layui-icon layui-icon-reply-fill">&nbsp;</span>最新评论</li>
					<li> <span class="layui-icon layui-icon-fire">&nbsp;</span>最热</li>
				</ul>

				<div class="layui-tab-content">
					<!-- 内容1 -->
					<div class="layui-tab-item layui-show">
						<!-- 第一块 -->
						<div v-for="index in info" class="layui-col-md12" style=" border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<div class="layui-col-md12 cont-1" style="padding-left: 1%; margin-bottom: 20px;">
										<a href="">{{index.title}}</a>
										<p>{{index.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;5K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div class="layui-col-md2 cont-r layui-hide-xs">
								<img :src="index.picInfo[0].url" alt="">
							</div>
						</div>
						<!-- 显示隐藏内容 -->
						<div v-for="(item, key) in cont" v-show="key<num" class="layui-col-md12" style=" border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<div class="layui-col-md12 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
										<a href="">{{item.title}}</a>
										<p>{{item.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div class="layui-col-md2 cont-r layui-hide-xs">
								<img :src="item.picInfo[0].url" alt="">
							</div>
						</div>
						<div @click="showMore" class="layui-col-md12 bod-bottom">
							{{txt}}
						</div>
						<!-- 结束 -->
					</div>
					<!-- 内容2 -->
					<div class="layui-tab-item">
						<div v-for="(index,i) in cont" class="layui-col-md12" style=" border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<div class="layui-col-md12 cont-1" style="padding-left: 1%; margin-bottom: 20px;">
										<a href="">{{index.title}}</a>
										<p>{{index.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;5K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div class="layui-col-md2 cont-r layui-hide-xs">
								<img :src="index.picInfo[0].url" alt="">
							</div>
						</div>
						<!-- 显示隐藏内容 -->
						<div v-for="(item, key) in toutiao" v-show="key<num" class="layui-col-md12" style=" border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<div class="layui-col-md12 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
										<a href="">{{item.title}}</a>
										<p>{{item.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div class="layui-col-md2 cont-r layui-hide-xs">
								<img :src="item.picInfo[0].url" alt="">
							</div>
						</div>
						<div @click="showMore" class="layui-col-md12 bod-bottom">
							{{txt}}
						</div>
						<!-- 隐藏内容结束 -->
					</div>
					<!-- 内容3 -->
					<div class="layui-tab-item">
						<div v-for="ind in toutiao" class="layui-col-md12" style=" border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<div class="layui-col-md12 cont-1" style="padding-left: 1%; margin-bottom: 20px;">
										<a href="">{{ind.title}}</a>
										<p>{{ind.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;5K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div class="layui-col-md2 cont-r layui-hide-xs">
								<img :src="ind.picInfo[0].url" alt="">
							</div>
						</div>
						
						<!-- 第一块 -->
						<div v-for="(item, key) in info" v-show="key<num" class="layui-col-md12" style=" border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<div class="layui-col-md12 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
										<a href="">{{item.title}}</a>
										<p>{{item.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div class="layui-col-md2 cont-r layui-hide-xs">
								<img :src="item.picInfo[0].url" alt="">
							</div>
						</div>
						<!-- 第一块结束 -->
						<div @click="showMore" class="layui-col-md12 bod-bottom">
							{{txt}}
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>

</template>

<script>
	export default {
		data: function() {
			return {
				maskShow: false,
				txt: '阅读更多',
				isShow: true,
				num:0,
				info: '',
				cont: '',
				toutiao:'',
			}
		},
		methods: {
			setMaskShow() {
				this.maskShow = !this.maskShow;
			},
			showMore() {
				this.isShow = !this.isShow;
				this.num = this.isShow ? 0 : this.info.length;
				this.txt = this.isShow ? '阅读更多' : '收起'
			},
			kaishi() {
				this.axios.get('https://www.apiopen.top/journalismApi').then((response) => {
					console.log(response.data.data);
					this.info = response.data.data.dy;
					this.cont = response.data.data.auto;
					this.toutiao = response.data.data.sports
				})
// 3007299054
			}
		},
		mounted: function() {
			this.kaishi();
		}

	}
</script>
