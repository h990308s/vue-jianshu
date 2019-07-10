<template>
	<!-- <div class="bod"> -->


	<!-- <div class="layui-row"> -->
	<!-- 右边内容 -->
	<div class="layui-col-md9">
		<div class="layui-tab layui-tab-brief" lay-filter="docDemoTabBrief">
			<ul class="layui-tab-title">
				<li class="layui-this">全部推荐</li>
				<li> <span class="layui-icon layui-icon-username">&nbsp;</span>推荐作者</li>
				<li> <span class="layui-icon layui-icon-app">&nbsp;</span>推荐专题</li>
			</ul>
			<div class="layui-tab-content" style="margin-top: 10px;">
				<!-- 内容1 -->
				<div class="layui-tab-item layui-show">
					<!-- 第一块 -->
					<div v-for="(index,i) in info" class="layui-col-md12" style=" padding-bottom: 15px; margin-top: 20px; border-bottom: 1px solid #f0f0f0;">
						<div class="layui-col-md10">
							<div class="spa">
								<span class="layui-icon layui-icon-auz">&nbsp;简书推荐专题</span>
							</div>
							<div class="cont1">
								<img class="layui-col-md2 layui-hide-xs" :src="index.picInfo[0].url">
								<div class="layui-col-md10 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
									<a href="">{{index.title}}</a>
									<p>{{index.digest}}</p>
									<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
								</div>
							</div>
						</div>
						<div v-show="index.tag" @click="sort(i)" class="layui-col-md2 cont-r">
							<a class="layui-hide-xs"><span>+关注</span></a>
							<a style="width: 100%;" class="layui-hide-md"><span>+关注</span></a>
						</div>
						<div v-show="!index.tag" @click="sort(i)" class="layui-col-md2 cont-r1">
							<a class="layui-hide-xs" id="show">
								<span id="show1">已关注</span>
								<span id="show2">取消关注</span>
							</a>
							<a class="layui-hide-md" style="width: 100%;" id="show">
								<span id="show1">已关注</span>
							</a>
						</div>
					</div>
					<!-- 第一块 -->
					<div v-for="(item, key) in items" v-show="key<num" class="layui-col-md12" style="padding-bottom: 15px; margin-top: 20px; border-bottom: 1px solid #f0f0f0;">
						<div class="layui-col-md10">
							<div class="spa">
								<span class="layui-icon layui-icon-auz">&nbsp;简书推荐专题</span>
							</div>
							<div class="cont1">
								<img class="layui-col-md2 layui-hide-xs" :src="item.src">
								<div class="layui-col-md10 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
									<a href="">{{item.h}}</a>
									<p>{{item.j}}</p>
									<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
								</div>
							</div>
						</div>
						<div class="layui-col-md2 cont-r">
							<a class="layui-hide-xs"><span>+关注</span></a>
							<a style="width: 100%;" class="layui-hide-md"><span>+关注</span></a>
						</div>
					</div>
					<!-- 第一块结束 -->
					<div @click="showMore" class="layui-col-md12 bod-bottom">
						{{txt}}
					</div>
				</div>

				<!-- 内容2 -->
				<div class="layui-tab-item">
					<div v-for="(inde,a) in cont" class="layui-col-md12" style=" padding-bottom: 15px; margin-top: 20px; border-bottom: 1px solid #f0f0f0;">
						<div class="layui-col-md10">
							
							<div class="cont1">
								<img class="layui-col-md2 layui-hide-xs" :src="inde.picInfo[0].url">
								<div class="layui-col-md10 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
									<a href="">{{inde.title}}</a>
									<p>{{inde.digest}}</p>
									<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
								</div>
							</div>
						</div>
						<div v-show="inde.tag"  @click="sort1(a)" class="layui-col-md2 cont-r">
							<a class="layui-hide-xs"><span>+关注</span></a>
							<a style="width: 100%;" class="layui-hide-md"><span>+关注</span></a>
						</div>
						<div v-show="!inde.tag" @click="sort1(a)" class="layui-col-md2 cont-r1">
							<a class="layui-hide-xs" id="show">
								<span id="show1">已关注</span>
								<span id="show2">取消关注</span>
							</a>
							<a class="layui-hide-md" style="width: 100%;" id="show">
								<span id="show1">已关注</span>
							</a>
						</div>
					</div>
					<!-- 第一块 -->
					<div v-for="(item, key) in items" v-show="key<num" class="layui-col-md12" style="margin-top: 10px; border-bottom: 1px solid #f0f0f0;">
						<div class="layui-col-md10">
							<div class="cont1">
								<img class="layui-col-md2 layui-hide-xs" :src="item.src">
								<div class="layui-col-md10 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
									<a href="">{{item.h}}</a>
									<p>{{item.j}}</p>
									<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
								</div>
							</div>
						</div>
						<div class="layui-col-md2 cont-r">
							<a class="layui-hide-xs"><span>+关注</span></a>
							<a style="width: 100%;" class="layui-hide-md"><span>+关注</span></a>
						</div>
					</div>
					<!-- 第一块结束 -->
					<div @click="showMore" class="layui-col-md12 bod-bottom">
						{{txt}}
					</div>

				</div>
				<!-- 内容3 -->
				<div class="layui-tab-item">
						<div v-for="(ind,s) in toutiao" class="layui-col-md12" style=" padding-bottom: 15px; margin-top: 20px; border-bottom: 1px solid #f0f0f0;">
							<div class="layui-col-md10">
								<div class="cont1">
									<img class="layui-col-md2 layui-hide-xs" :src="ind.picInfo[0].url">
									<div class="layui-col-md10 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
										<a href="">{{ind.title}}</a>
										<p>{{ind.digest}}</p>
										<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
									</div>
								</div>
							</div>
							<div v-show="ind.tag"  @click="sort2(s)" class="layui-col-md2 cont-r">
								<a class="layui-hide-xs"><span>+关注</span></a>
								<a style="width: 100%;" class="layui-hide-md"><span>+关注</span></a>
							</div>
							<div v-show="!ind.tag" @click="sort2(s)" class="layui-col-md2 cont-r1">
								<a class="layui-hide-xs" id="show">
									<span id="show1">已关注</span>
									<span id="show2">取消关注</span>
								</a>
								<a class="layui-hide-md" style="width: 100%;" id="show">
									<span id="show1">已关注</span>
								</a>
							</div>
						</div>

					<!-- 第一块 -->
					<div v-for="(item, key) in cont" v-show="key<num" class="layui-col-md12" style="margin-top: 10px; border-bottom: 1px solid #f0f0f0;">
						<div class="layui-col-md10">
							<div class="cont1">
								<img class="layui-col-md2 layui-hide-xs" :src="item.picInfo[0].url">
								<div class="layui-col-md10 cont-1" style="padding-left: 13px; margin-bottom: 20px;">
									<a href="">{{item.title}}</a>
									<p>{{item.digest}}</p>
									<span class="layui-icon layui-icon-app">&nbsp;116.2K篇文章 · 2361.9K人关注</span>
								</div>
							</div>
						</div>
						<div class="layui-col-md2 cont-r">
							<a class="layui-hide-xs"><span>+关注</span></a>
							<a style="width: 100%;" class="layui-hide-md"><span>+关注</span></a>
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
	<!-- </div> -->
	<!-- </div> -->
</template>

<style>
	#show:hover #show1 {
		display: none;

	}

	#show:hover {
		background-color: #f0f0f0;
	}

	#show2 {
		display: none;
	}

	#show:hover #show2 {
		display: block;

	}

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
		font-size: 15px;
		font-weight: 700;
		color: #333;
		display: block;
		margin: 0 0 7px;
	}

	.cont-1 p {
		color: #969696;
		font-size: 12px;
		margin: 0 0 7px;
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
		cursor: pointer;
	}

	.cont-r {
		margin-top: 30px;
	}

	.cont-r a:hover {
		background: rgb(61, 185, 34);
	}

	.cont-r a span {
		display: block;
		font-size: 16px;
		font-weight: 400;
		color: #FFFFFF;
		text-align: center;
		line-height: 40px;
	}

	.cont-r1 a {
		display: block;
		width: 100px;
		height: 40px;
		background-color: #ffffff;
		border-radius: 20px;
		cursor: pointer;
		border: 1px solid hsla(0, 0%, 59%, .6);
	}

	.cont-r1 {
		margin-top: 30px;
	}

	.cont-r1 a span {
		display: block;
		font-size: 16px;
		font-weight: 400;
		text-align: center;
		line-height: 40px;
		color: #8c8c8c;
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
		color: #FFFFFF;
	}
</style>

<script>
	import {
		truncate
	} from 'fs';
	export default {
		data() {
			return {
				downIcon: true,
				downIcon1: false,
				downIcon2: false,
				downIcon3: false,
				seen: true,
				txt: '阅读更多',
				isShow: true,
				info: [],
				cont: '',
				toutiao: '',
				num: 0,
				i: -1,
				items: [{

						h: "自然科普",
						j: "是：老司机/奶爸/吃货写：职场的坑/父女的哏/美食的魂...",
						src: require('../assets/12.webp')

					},
					{
						h: "北落西门",
						j: "简书签约作者，商业管理优秀作者，视觉优秀作者，顺丰速运集团前高管...",
						src: require('../assets/1.webp')

					},
					{
						h: "无限猴子",
						j: "一只有限写作的无限猴子~ 版权合作事宜请联系行距文化：pub@...",
						src: require('../assets/3.webp')

					}
				],
				one: [{

				}],
			}
		},
		methods: {
			sort(i) {
				this.info[i].tag = !this.info[i].tag;
			},
			sort1(a) {
				this.cont[a].tag = !this.cont[a].tag
			},
			sort2(s) {
				this.toutiao[s].tag = !this.toutiao[s].tag
			},
			showMore() {
				this.isShow = !this.isShow;
				this.num = this.isShow ? 0 : this.items.length;
				this.txt = this.isShow ? '阅读更多' : '收起'
			},
			kaishi() {
				// 调用API获取数组
				this.axios.get('https://www.apiopen.top/journalismApi').then((response) => {
					this.info = response.data.data.dy;
					this.cont = response.data.data.auto;
					// console.log(response.data.data.auto);
					this.toutiao = response.data.data.tech;
					/* 给所取api内容字段tag设置true/false,来实现关注按钮切换 */
					for (a = 0; a < this.cont.length; a++) {
						this.cont[a].tag = true;
						console.log(this.cont[a].tag)
					};
					for (i = 0; i < this.info.length; i++) {
						this.info[i].tag = true;
						console.log(!this.info[i].tag)
					};
					
				})
			}

		},
		mounted: function() {
			this.kaishi();
		}

	}
</script>
