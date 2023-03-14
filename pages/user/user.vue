<template>
	<view style="bigBox">
		<image src="../../static/1.jpg" class="bg-img" aspectFill ></image>
		<div class="div1" style="text-align: center;">
			<div class="div1-1">
				<!-- <image src="../../static/logo.png" width="50px" height="50px"></image> -->
			</div>
			<div class="div1-2" style="color: white; font-weight: 600; margin: 5px;">
				点击登录
				<!-- <image src="../../static/logo.png" width="50px" height="50px"></image> -->
			</div>
		</div>
		<div class="div2">
			<el-collapse>
			  <el-collapse-item title="积分" name="1">
			    <!-- <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div> -->
			    <!-- <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div> -->
			  </el-collapse-item>
			  <el-collapse-item title="昵称" name="2">
			   
			  </el-collapse-item>
			  <el-collapse-item title="效率 Efficiency" name="3">
			   
			  </el-collapse-item>
			  <el-collapse-item title="可控 Controllability" name="4">
			   
			  </el-collapse-item>
			  <el-collapse-item title="积分" name="1">
			    <!-- <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div> -->
			    <!-- <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div> -->
			  </el-collapse-item>
			  <el-collapse-item title="昵称" name="2">
			   
			  </el-collapse-item>
			  <el-collapse-item title="效率 Efficiency" name="3">
			   
			  </el-collapse-item>
			  <el-collapse-item title="可控 Controllability" name="4">
			   
			  </el-collapse-item>
			</el-collapse>
		</div>
	<!-- <userPage></userPage> -->
	</view>
</template>
<script>
	import userPage from "../../components/userPage.vue"
	export default {
		components:{userPage},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
.bigBox{
	  display: flex;
	  flex-direction: column; 
}
/deep/.el-collapse {
	border-top: 1px solid #ffffff;
	border-bottom: 1px solid #ffffff;
	width: 97%;
}
.bg-img{
    position: fixed;
   width: 100%;
    /* height: 100%; */
    top: 0;
    left: 0;
    z-index: -1;
}
.div1{
	width: 100%;
	/* height: 400px; */
	/* border: 1px solid black; */
}

.div1 >.div1-1{
	width: 100px;
	height: 100px;
	/* border: 1px solid black; */
	border-radius: 150px;
	margin-top: 115px;
	margin-left: 153px;
	background: url('../../static/logo.png');
	background-repeat: no-repeat;
	background-size: 100% 100%;
}
.div2{
	width: 100%;
	/* height: 520px; */
	/* border: 1px solid black; */
	background-color: white;
	border-radius: 35px 53px 0px 0px;
	padding: 10px;
	position: absolute;
}
</style>
