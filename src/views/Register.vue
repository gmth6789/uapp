<template>
	<view class="container container24325">
		<view class="flex flex-wrap diygw-col-24 flex-direction-column justify-center items-center flex-clz">
			<image src="/static/tx-nxs4.png" class="image-size diygw-image diygw-col-0 image-clz" mode="widthFix"></image>
			<diy-navbar :isFixed="true" backUrl="/pages/index" bgColor="green" :isHome="true" :isBack="true">
				<!-- #ifndef VUE3 -->
				<block slot="backText"> กลับ </block>
				<block slot="content"> เข้าสู่ระบบ </block>
				<!-- #endif -->
				<!-- #ifdef VUE3 -->
				<template v-slot:backText> กลับ </template>
				<template v-slot:content> เข้าสู่ระบบ </template>
				<!-- #endif -->
			</diy-navbar>
		</view>
		<form @submit="submitForm" class="flex diygw-form flex-direction-column diygw-col-24">
			<view class="diygw-form-item diygw-col-24 flex-direction-column noborder">
				<view class="title diygw-col-24"> ยูสเซอร์เนม </view>
				<view class="input solid radius">
					<image src="" class="diygw-icon radius"></image>
					<input class="flex1" maxlength="20" :focus="formData.usenameFocus" name="usename" comfirm-type="done" type="text" v-model="form.usename" กรุณากรอกยูสเซอร์เนมของท่าน placeholder="กรุณากรอกยูสเซอร์เนมของท่าน" />
				</view>
			</view>
			<view class="diygw-form-item diygw-col-24 flex-direction-column">
				<view class="title diygw-col-24"> รหัสผ่าน </view>
				<view class="input solid radius">
					<image src="/static/global/grid1.png" class="diygw-icon radius"></image>
					<input class="flex1" :focus="formData.passwordFocus" name="password" comfirm-type="done" type="password" v-model="form.password" placeholder="กรุณากรอกรหัสผ่าน" />
				</view>
			</view>
			<view class="flex flex-wrap diygw-col-24 justify-between flex1-clz">
				<view class="diygw-col-0 text-clz diygw-text-md"> ลืมรหัสผ่าน </view>
				<view class="diygw-col-0 text1-clz diygw-text-md"> สมัครสมาชิก </view>
			</view>
			<view class="flex diygw-col-24 button-clz">
				<button class="diygw-btn pink radius flex-sub margin-xs button-button-clz">เข้าสู่ระบบ</button>
			</view>
		</form>
		<view class="flex flex-wrap diygw-col-24 justify-center items-center flex2-clz">
			<view class="flex diygw-col-8">
				<view class="diygw-pzx" style="border-bottom: 2px solid #eee"></view>
			</view>
			<view class="diygw-col-0 text2-clz diygw-text-md text-cyan"> เข้าสู่ระบบด้วยวิธีอื่นๆ </view>
			<view class="flex diygw-col-8">
				<view class="diygw-pzx" style="border-bottom: 2px solid #eee"></view>
			</view>
		</view>
		<view class="flex flex-wrap diygw-col-24 justify-center items-center flex3-clz">
			<image src="/static/dyn_detail_qq.png" class="image1-size diygw-image diygw-col-0" mode="widthFix"></image>
			<image src="/static/dyn_detail_wechat.png" class="image2-size diygw-image diygw-col-0" mode="widthFix"></image>
			<image src="/static/dyn_detail_weibo.png" class="image3-size diygw-image diygw-col-0" mode="widthFix"></image>
		</view>
		<view class="flex flex-wrap diygw-col-24 justify-around diygw-bottom flex11-clz">
			<view class="flex flex-wrap diygw-col-0 flex-direction-column items-center">
				<view class="flex diygw-col-24">
					<view class="diygw-avatar radius bg-none">
						<image mode="aspectFit" class="diygw-avatar-img radius" src="/static/global/grid1.png"></image>
					</view>
				</view>
				<view class="diygw-col-0"> หน้าหลัก </view>
			</view>
			<view class="flex flex-wrap diygw-col-0 flex-direction-column items-center">
				<view class="flex diygw-col-24">
					<view class="diygw-avatar radius bg-none">
						<image mode="aspectFit" class="diygw-avatar-img radius" src="/static/global/grid2.png"></image>
					</view>
				</view>
				<view class="diygw-col-0"> ภารกิจ </view>
			</view>
			<view class="flex flex-wrap diygw-col-0 flex-direction-column items-center">
				<view class="flex diygw-col-24">
					<view class="diygw-avatar radius bg-none">
						<image mode="aspectFit" class="diygw-avatar-img radius" src="/static/global/grid3.png"></image>
					</view>
				</view>
				<view class="diygw-col-0 text16-clz"> 10 </view>
				<view class="diygw-col-0"> อันดับ </view>
			</view>
			<view class="flex flex-wrap diygw-col-0 flex-direction-column items-center">
				<view class="flex diygw-col-24">
					<view class="diygw-avatar radius bg-none">
						<image mode="aspectFit" class="diygw-avatar-img radius" src="/static/global/grid5.png"></image>
					</view>
				</view>
				<view class="diygw-col-0"> แชท </view>
			</view>
			<view class="flex flex-wrap diygw-col-0 flex-direction-column items-center">
				<view class="flex diygw-col-24">
					<view class="diygw-avatar radius bg-none">
						<image mode="aspectFit" class="diygw-avatar-img radius" src="/static/global/grid4.png"></image>
					</view>
				</view>
				<view class="diygw-col-0"> ข้อมูล </view>
			</view>
		</view>
		<view class="version text-grey flex-direction-column flex diygw-col-24 justify-center align-center">
			<view> DIY官网代码生成器生成 </view>
			<view> http://www.diygw.com </view>
		</view>
		<view class="clearfix"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				//用户全局信息
				userInfo: {},
				//页面传参
				globalOption: {},
				//自定义全局变量
				globalData: {},
				form: {
					usename: '',
					password: ''
				},
				formData: {
					usenameFocus: false,
					passwordFocus: false
				}
			};
		},
		onShow() {
			this.setCurrentPage(this);
		},
		onLoad(option) {
			this.setCurrentPage(this);
			if (option) {
				this.setData({
					globalOption: this.getOption(option)
				});
			}

			this.init();
		},
		methods: {
			async init() {
				await this.initResetform();
			},
			initResetform() {
				this.initform = JSON.stringify(this.form);
			},
			resetForm() {
				this.form = JSON.parse(this.initform);
			},

			async submitForm(e) {
				this.validateForm = this.Validate({
					usename: {
						required: {
							message: 'กรุณากรอกยูสเซอร์เนมให้ถูกต้อง'
						}
					},
					password: {
						required: {
							message: '密码不能为空'
						}
					}
				});
				if (!this.validateForm.checkForm(e)) {
					let data = this.validateForm.errorList[0];
					this.showToast(data.msg, 'none');
					return false;
				} else {
					//保存数据
					let param = e.detail.value;
					let url = '';
					if (!url) {
						this.showToast('请先配置表单提交地址', 'none');
						return false;
					}
					let header = {};

					let res = await this.$http.post(url, param, header, 'json');

					if (res.code == 200) {
						this.showToast(res.msg, 'success');
					} else {
						this.showToast(res.msg, 'error');
					}
				}
			}
		}
	};
</script>

<style lang="scss" scoped>
	.flex-clz {
		z-index: 100;
		height: 180px;
	}
	.image-clz {
		border-bottom-left-radius: 50%;
		box-shadow: 0px 1px 3px rgba(31, 31, 31, 0.16);
		overflow: hidden;
		border-top-left-radius: 50%;
		border-top-right-radius: 50%;
		border-bottom-right-radius: 50%;
	}
	.image-size {
		height: 80px !important;
		width: 80px !important;
	}
	.flex1-clz {
		margin-left: 15px;
		z-index: 100;
		width: calc(100% - 15px - 15px) !important;
		margin-top: 15px;
		margin-bottom: 15px;
		margin-right: 15px;
	}
	.text-clz {
		color: #9c9c9c;
	}
	.text1-clz {
		color: #9c9c9c;
	}
	.button-clz {
		margin-left: 10px;
		width: calc(100% - 10px - 10px) !important;
		margin-top: 10px;
		margin-bottom: 10px;
		margin-right: 10px;
	}
	.button-button-clz {
		font-size: 20px !important;
		margin: 3px !important;
		padding: 23px !important;
	}
	.flex2-clz {
		z-index: 100;
	}
	.text2-clz {
		margin-left: 5px;
		margin-top: 5px;
		margin-bottom: 5px;
		margin-right: 5px;
	}
	.flex3-clz {
		margin-left: 5px;
		z-index: 100;
		width: calc(100% - 5px - 5px) !important;
		margin-top: 25px;
		margin-bottom: 5px;
		margin-right: 5px;
	}
	.image1-size {
		height: 40px !important;
		width: 40px !important;
	}
	.image2-size {
		height: 40px !important;
		width: 40px !important;
	}
	.image3-size {
		height: 40px !important;
		width: 40px !important;
	}
	.flex11-clz {
		padding-top: 2px;
		box-shadow: 0px 1px 4px 2px rgba(31, 31, 31, 0.16);
		overflow: visible;
		left: 0px;
		bottom: 0px;
		padding-left: 2px;
		padding-bottom: 2px;
		padding-right: 2px;
	}
	.text16-clz {
		padding-top: 2px;
		border-bottom-left-radius: 60px;
		z-index: 1;
		color: #ffffff;
		padding-left: 3px;
		font-size: 10rpx !important;
		padding-bottom: 2px;
		border-top-right-radius: 60px;
		right: -5px;
		background-color: #ff0000;
		overflow: hidden;
		top: -5px;
		border-top-left-radius: 60px;
		border-bottom-right-radius: 60px;
		position: absolute;
		padding-right: 3px;
	}
	.container24325 {
		padding-left: 0px;
		padding-right: 0px;
	}
	.container24325 {
	}
</style>
