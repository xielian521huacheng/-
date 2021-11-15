<template>
	<div class="login">
		<s-header :name="type == 'login' ? '登录' : '注册'" :back="'/home'"></s-header>
		<img class="logo" src="//s.weituibao.com/1591183219275/200181591183191_.pic.jpg" alt="" />
		<div v-if="type == 'login'" class="login-body login">
			<van-form @submit="onSubmit">
				<van-field v-model="username" name="username" label="用户名" placeholder="用户名" :rules="[{ required: true, message: '请填写用户名' }]" />
				<van-field v-model="password" type="password" name="password" label="密码" placeholder="密码" :rules="[{ required: true, message: '请填写密码' }]" />
				<div class="verify">
					<Verify ref="loginVerifyRef" @error="error" :showButton="false" @success="success" :width="'100%'" :height="'40px'" :fontSize="'16px'" :type="2"></Verify>
				</div>
				<div style="margin: 16px;">
					<div class="link-register" @click="toggle('register')">立即注册</div>
					<van-button round block type="info" color="#c40000" native-type="submit">登录</van-button>
				</div>
			</van-form>
		</div>
		<div v-else class="login-body register">
			<van-form @submit="onSubmit">
				<van-field v-model="username1" name="username1" label="用户名" placeholder="用户名" :rules="[{ required: true, message: '请填写用户名' }]" />
				<van-field v-model="password1" type="password" name="password1" label="密码" placeholder="密码" :rules="[{ required: true, message: '请填写密码' }]" />
				<div class="verify">
					<Verify ref="loginVerifyRef" @error="error" :showButton="false" @success="success" :width="'100%'" :height="'40px'" :fontSize="'16px'" :type="2"></Verify>
				</div>
				<div style="margin: 16px;">
					<div class="link-login" @click="toggle('login')">已有登录账号</div>
					<van-button round block type="info" color="#c40000" native-type="submit">注册</van-button>
				</div>
			</van-form>
		</div>
	</div>
</template>

<script>
export default {
	data() {},

	methods: {}
};
</script>

<style></style>
