<template>
  <div class="user-page">
    <div class="user-info">
      <div class="avatar">
        <!-- <img src="./assets/avatar.png" alt="Avatar"> -->
      </div>
	  <view class="uni-flex uni-column">
		  
      <div class="info">
		<view>
        <router-link to = "/" class="router-link">
			<div class="nickname">{{ user.nickname }}</div>
			<image class="touxiang" src="../static/data.png"></image>
		</router-link>
		</view>
		
		<view>
		<router-link to = "/" class="router-link">
        <div class="gender">{{ user.gender }}</div>
		</router-link>
		</view>
		
		<view>
		<router-link to = "/" class="router-link">
        <div class="position">{{ user.position }}</div>
		</router-link>
		</view>
		
		<view>
		<router-link to = "/" class="router-link">
        <div class="job-number">{{ user.jobNumber }}</div>
		</router-link>
		</view>
		
		<view>
		<router-link to = "/" class="router-link">
        <div class="project">{{ user.project }}</div>
		</router-link>
		</view>
		
		<view>
		<router-link to = "/" class="router-link">
        <div class="score">{{ user.score }}</div>
		</router-link>
		</view>
		
		<view>
		<router-link to="/" class="router-link">待办事项</router-link>
		</view>
		
		<view>
        <router-link to="/logs" class="router-link">日志</router-link>
		</view>
      </div>
	  
	  </view>
	  
    </div>
    <div class="menu">
	  <button type="warn">
      <router-link to="/logout">退出登录</router-link>
	  </button>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
	name:"userPage",
  data() {
    return {
      user: {
        nickname: '小明',
        gender: '男',
        position: '开发工程师',
        jobNumber: '123456',
        project: '项目A',
        score: 1000
      }
    };
  }
};
</script>


<style>
/* 路由链接样式 */
.router-link {
  display: inline-block;
  position: relative;
  padding: 0.5rem 1rem;
  font-size: 1.2rem;
  width: 400px;
  font-weight: 600;
  text-decoration: none;
  color: #00aa7f;
  background-image: linear-gradient(to bottom right, #ffffff, #ffffff);
  border-radius: 0.5rem;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  transition: all 0.3s ease;
}

.router-link:before {
  content: "";
  position: absolute;
  top: -0.5rem;
  left: -0.5rem;
  width: calc(100% + 1rem);
  height: calc(100% + 1rem);
  background-color: #fff;
  z-index: -1;
  transform: translate(-20%, -20%) rotate(45deg);
  transition: all 0.3s ease;
  opacity: 0;
}

.router-link:hover:before {
  transform: translate(-20%, -20%) rotate(0deg);
  opacity: 0.2;
}

.router-link:hover {
  background-image: linear-gradient(to bottom right, #ff5e62, #ff7f50);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

.router-link.active {
  background-image: linear-gradient(to bottom right, #ff5e62, #ff7f50);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

.user-info{
	margin-top: 10px;
	font-size: 30px;
}

.touxiang{
	margin-top: -50px;
	float: right;
	height: 80px;
	width: 80px;
}

</style>