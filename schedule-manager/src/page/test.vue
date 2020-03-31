<template>
  	<div class="login_page fillcontain">
	  	{{res}}
  	</div>
</template>

<script>
	import {login, getAdminInfo} from '@/api/getData'
	import {mapActions, mapState} from 'vuex'
	import fetch from '@/config/fetch'

	export default {
	    data(){
			return {
				res:"test"
			}
		},
		mounted(){
			
		},
		computed: {
			
		},
		created(){
			let v = this;
			v.login();
		},
		methods: {
			async login(){
				let v = this;
				v.res = await  fetch('/applet/union/login', {"account":"729056559@qq.com","password":"2768024c94054878a781a4110d74c850"}, 'POST');
				v.sendSms();
			},
			sendSms(){
				let v = this;
				fetch('/applet/union/sendSmsCode', {"phone":"111"}, 'POST');
			}
		},
		watch: {
			
		}
	}
</script>

<style lang="less" scoped>
	
</style>
