<template>
	<div>
		<a href="/"><img src="../images/logo.png" alt=""></a>
		<div class="layui-row nav">
			<div class="layui-row" style="height: 20px;"></div>
			<div class="layui-row" style="height: 50px;">
				<div class="layui-col-md3 wh"></div>
				<div class="layui-col-md6 center">
					<div class="layui-col-md1 wh"></div>
					<a href="/denglu"><div class="layui-col-md4 cla" style="color: rgb(150,150,150); cursor: pointer;">登录</div></a>
					<div class="layui-col-md1 wh"></div>
					<div class="layui-col-md1 wh"></div>
					<a href="/zhuce"><div class="layui-col-md4 clk">注册</div></a>
					<div class="layui-col-md1 wh"></div>
				</div>
				<div class="layui-col-md3 wh"></div>
			</div>
			<div class="layui-row" style="height: 50px;"></div>
			<div class="layui-row inp" style="border-radius: 5px 5px 0 0; border: 1px solid #c8c8c8;">
				<i class="layui-icon layui-icon-username">&nbsp;&nbsp;</i><input type="text" placeholder="你的昵称">
			</div>
			<div class="layui-row inp" style="border-left: 1px solid #c8c8c8; border-right: 1px solid #c8c8c8; border-top: none;">
				<i class="layui-icon layui-icon-password">&nbsp;&nbsp;</i><input type="text" placeholder="手机号">
			</div>
			<div class="layui-row inp" style="border: 1px solid #c8c8c8; border-radius: 0 0 5px 5px;">
				<i class="layui-icon layui-icon-password">&nbsp;&nbsp;</i><input type="text" placeholder="设置密码">
			</div>
			<div class="layui-row" style="height: 20px;"></div>
			<div class="layui-row dl">
				注册
			</div>
			<div class="layui-row" style="height: 20px;"></div>
			<div class="layui-row tk">
				<p>点击“注册”即表示您同意并愿意遵守简书</p>
				<p><a href=""><span>用户协议</span></a>  和  <a href=""><span>隐私政策</span></a></p>
			</div>
			<div class="layui-row" style="height: 30px;"></div>
			<fieldset class="layui-field-title">
				<legend>&nbsp;&nbsp;&nbsp;社区账号直接注册&nbsp;&nbsp;</legend>
			</fieldset>
			<div class="layui-row" style="height: 10px;"></div>
			<div class="layui-row foot">
				<div class="layui-col-md3" style="border-bottom: 1px solid #FFFFFF;">
				</div>
				<div class="layui-col-md3">
					<i class="layui-icon layui-icon-login-wechat" style="color: rgb(0,187,41); cursor: pointer;"></i>
				</div>
				<div class="layui-col-md3">
					<i class="layui-icon layui-icon-login-qq" style="color: rgb(73,138,213); cursor: pointer;"></i>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
</script>

<style scoped>
	*{
		background-color: rgb(241,241,241);
	}
	.nav{
		width: 30%;
		box-shadow:#EEEEEE 0 0 5px 2px;
		border-radius: 5px;
		margin: 0 auto;
		height: 510px;
		margin-top: -50px;
		background-color: #FFFFFF;
	}
	.wh{
		border-bottom: 1px solid #FFFFFF;
	}
	.center{
		text-align: center;
		font-size: 18px;
		font-weight: bold;
		line-height: 50px;
	}
	.clk{
		color: rgb(234,111,90);
		border-bottom: 2px solid rgb(234,111,90);
		cursor: pointer;
	}
	.cla:hover{
		border-bottom: 2px solid rgb(234,111,90);
	}
	.inp{
		width: 80%;
		margin: 0 auto;
		height: 50px;
		line-height: 50px;
		text-align: center;
		background-color: rgb(247,247,247);
	}
	.inp input{
		background-color: rgb(247,247,247);
		border: none;
		width: 80%;
	}
	.inp i{
		color: rgb(150,150,150);
		font-size: 20px;
	}
	.rad{
		width: 80%;
		height: 50px;
		line-height: 50px;
		margin: 0 auto;
		color: rgb(150,150,150);
	}
	.rad p{
		float: right;
		cursor: pointer;
	}
	.rad p:hover{
		color: #000000;
	}
	.dl{
		width: 80%;
		height: 40px;
		background-color: rgb(66,192,46);
		border-radius: 25px;
		margin: 0 auto;
		text-align: center;
		line-height: 40px;
		font-size: 18px;
		color: #FFFFFF;
		cursor: pointer;
	}
	.dl:hover{
		background-color: rgb(61,185,34);
	}
	.tk{
		width: 60%;
		margin: 0 auto;
	}
	.tk p{
		font-size: 12px;
		text-align: center;
		color: rgb(150,150,150);
	}
	.tk a{
		color: #3194d0;
		text-decoration: none;
	}
	fieldset{
		width: 60%;
		margin: 0 auto;
		border-top:1px solid rgb(150,150,150);
		text-align: center;
		color: rgb(150,150,150);
		font-size: 12px;
	}
	.foot{
		width: 60%;
		margin: 0 auto;
		text-align: center;
		
	}
	.foot i{
		font-size: 30px;
	}
</style>
