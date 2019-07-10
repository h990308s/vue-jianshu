<template>
	<div>
		<div class="layui-hide-xs">
			<top />
			<div class="layui-row" style="height: 100px;"></div>
			<div class="layui-row chat">
				<div class="layui-col-md4 chat_li">
					<a href="/pinglun">
						<div class="layui-col-md12" style="background: rgb(240, 241, 241);">
							<i class="el-icon-chat-square"></i>&nbsp;&nbsp;&nbsp;&nbsp;评论
						</div>
					</a>
					<a href="/tixe">
						<div class="layui-col-md12">
							<i class="el-icon-message"></i>&nbsp;&nbsp;&nbsp;&nbsp;简信
						</div>
					</a>
					<a href="/tougao">
						<div class="layui-col-md12">
							<i class="layui-icon layui-icon-upload-drag"></i>&nbsp;&nbsp;&nbsp;&nbsp;投稿请求
						</div>
					</a>
					<a href="/zan">
						<div class="layui-col-md12">
							<i class="el-icon-cloudy"></i>&nbsp;&nbsp;&nbsp;&nbsp;喜欢和赞
						</div>
					</a>
					<a href="/guanzhu">
						<div class="layui-col-md12">
							<i class="layui-icon layui-icon-username"></i>&nbsp;&nbsp;&nbsp;&nbsp;关注
						</div>
					</a>
				</div>
				<div class="layui-col-md8 chat_item">
					<div class="layui-row item">
						<h3>全部评论</h3>
					</div>
					<div class="layui-row" style="height: 20px;"></div>
					<div class="layui-row lib" v-for="(index,ky) in syk" :key="ky">
						<div class="layui-col-md1"><img :src="index.picInfo[0].url" alt=""></div>
						<div class="layui-col-md8 left">
							<p>{{index.title}}</p>
							<span>{{index.source}}</span>
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- 手机 -->
		<div class="layui-hide-sm">
			<sjdh></sjdh>
			<div class="layui-row" style="height: 60px;"></div>
			<div class="layui-row chat1">
				<div class="layui-col-md4 chat_li">
					<div class="layui-col-md12" style="background: rgb(240, 241, 241);">
						<a href="/pinglun"><i class="el-icon-chat-square"></i>&nbsp;&nbsp;&nbsp;&nbsp;评论</a>
						<p class="zhan" style="float: right; color: rgb(233,111,90);" @click="show=!show">展开全部 <i class="layui-icon layui-icon-add-circle-fine"></i></p>
					</div>
					<div style="height: 100%;" v-if="!show">
						<a href="/tixe">
							<div class="layui-col-md12">
								<i class="el-icon-message"></i>&nbsp;&nbsp;&nbsp;&nbsp;简信
							</div>
						</a>
						<a href="/tougao">
							<div class="layui-col-md12">
								<i class="layui-icon layui-icon-upload-drag"></i>&nbsp;&nbsp;&nbsp;&nbsp;投稿请求
							</div>
						</a>
						<a href="/zan">
							<div class="layui-col-md12">
								<i class="el-icon-cloudy"></i>&nbsp;&nbsp;&nbsp;&nbsp;喜欢和赞
							</div>
						</a>
						<a href="/guanzhu">
							<div class="layui-col-md12">
								<i class="layui-icon layui-icon-username"></i>&nbsp;&nbsp;&nbsp;&nbsp;关注
							</div>
						</a>
					</div>
				</div>
				<div class="layui-col-md8 chat_item">
					<div class="layui-row item">
						<h3>全部评论</h3>
					</div>
					<div class="layui-row" style="height: 20px;"></div>
					<div class="layui-row lib" v-for="(inde,ky) in sy" :key="ky">
						<div class="layui-col-md1 layui-col-xs2"><img :src="inde.picInfo[0].url" alt=""></div>
						<div class="layui-col-md8 layui-col-xs9 left">
							<p>{{inde.title}}</p>
							<span>{{inde.source}}</span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import top from '../top2.vue'
	import sjdh from '../sjdh.vue'
	export default {
		name: 'Home',
		components: {
			top,
			sjdh
		},
		data() {
			return {
				show: true,
				sky: '',
				sy: ''
			}
		},
		created(){
			this.axios.get('https://www.apiopen.top/journalismApi').then((response) => {
			console.log(response.data.data)
			this.syk=response.data.data.war
			this.sy=response.data.data.auto
			})
		}
	}
</script>

<style scoped lang="scss">
	.chat {
		font-weight: '微软雅黑';
		width: 65%;
		margin: 0 auto;

		.chat_li {
			div {
				width: 80%;
				height: 50px;
				line-height: 50px;
				font-size: 16px;
				color: #000000;
				cursor: pointer;
			}

			div:hover {
				background: rgb(240, 241, 241);
			}

			i {
				color: rgb(233, 111, 90);
				margin-left: 20px;
				font-size: 20px;
			}
		}

		.chat_item {
			.item {
				height: 50px;
				line-height: 50px;
				border-bottom: 1px solid #cccccc;
			}

			.lib {
				width: 90%;
				margin-top: 20px;
				img {
					width: 100%;
					border-radius: 10%;
				}

				p {
					font-size: 16px;
					font-weight: bold;
				}

				span {
					font-size: 12px;
					line-height: 30px;
				}

				.left {
					margin-left: 20px;
				}
			}
		}
	}

	.chat1 {
		width: 90%;
		margin: 0 auto;
		font-weight: '微软雅黑';

		.chat_li {
			div {
				width: 100%;
				height: 50px;
				line-height: 50px;
				font-size: 16px;
				color: #000000;
				cursor: pointer;

				p {
					i {
						margin-right: 20px;
					}
				}
			}

			a {
				i {
					color: rgb(233, 111, 90);
					margin-left: 20px;
					font-size: 20px;
				}
			}
		}

		.chat_item {
			.item {
				height: 50px;
				line-height: 50px;
				border-bottom: 1px solid #cccccc;
				text-align: center;
			}

			.lib {
				width: 90%;
				margin: 20px 0;
				img {
					width: 100%;
					border-radius: 10%;
					border: 1px solid #cccccc;
					margin-left: 5px;
					height: 50px;
				}

				p {
					font-size: 16px;
					font-weight: bold;
				}

				span {
					font-size: 12px;
					line-height: 10px;
				}

				.left {
					margin-left: 20px;
				}
			}
		}
	}
</style>
