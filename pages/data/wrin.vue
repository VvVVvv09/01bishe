<template>
	<view >
		<div style="text-align: center;">
			<div class="div1" >
				<span>数据分析</span>
			</div>
			<el-select v-model="value" placeholder="请选择">
			    <el-option
			      v-for="item in options"
			      :key="item.value"
			      :label="item.label"
			      :value="item.value">
			    </el-option>
			  </el-select>
		</div>
		<div style="margin: 5px;">
			<span style="font-size: 18; font-weight: bold;">初始数据</span>
			<el-table
			   :data="tableData"
			   border
			   style="width: 100%">
			   <el-table-column
			     prop="date"
			     label=" "
			     >
			   </el-table-column>
			   <el-table-column
			     prop="name"
			     label="姓名"
			     >
			   </el-table-column>
			   <el-table-column
			     prop="address"
			     label="地址">
			   </el-table-column>
						<el-table-column
						  prop="a"
						  label="d">
						</el-table-column>
			 </el-table>
		</div>
		<div style="margin: 5px;">
			<div class="chart" id="chart" style="height: 500px"></div>
		</div>
	</view>
</template>

<script>
export default {
	    data() {
	      return {
			  tableData: [{
			   date: '两小时前',
			   name: '王小虎',
			   address: '上海市普陀区金沙江路 1518 弄'
			 }, {
			   date: '一小时前',
			   name: '王小虎',
			   address: '上海市普陀区金沙江路 1517 弄',
							  a:'1'
			 }, {
			   date: '当前',
			   name: '王小虎',
			   address: '上海市普陀区金沙江路 1519 弄'
			 },],
	        options: [{
	          value: '选项1',
	          label: '黄金糕'
	        }, {
	          value: '选项2',
	          label: '双皮奶'
	        }, {
	          value: '选项3',
	          label: '蚵仔煎'
	        }, {
	          value: '选项4',
	          label: '龙须面'
	        }, {
	          value: '选项5',
	          label: '北京烤鸭'
	        }],
	        value: ''
	      }
	    },
		methods: {
			createChart() {
				      var myChart =this.$echarts.init(document.getElementById('chart'))
				      let option = {
						  title: {
						      text: '时实数据'
						    },
				    // x轴
				    xAxis: {
				        // 一般情况 x轴都是 category
				        type: 'category',
				        data: ['转速', '温度', '压强', '扭矩', '温度']
				    },
				    // y 轴
				    yAxis: {
				        // 一般情况y轴也都是value型，数据来自series
				        type: 'value',
						 axisLine: {
						        show: false
						    },
						    axisTick: {
						        show: false
						    }
				    },
				    // 整个区域
				    series: [
				      {
				        name: 'Highest',
				        type: 'line',
				        data: [103, 121, 133, 113, 12, 12, 9],
						lineStyle:{
						color:'#7ec5cc'
						},
				        // markPoint: {
				        //   data: [
				        //     { type: 'max', name: 'Max' },
				        //     { type: 'min', name: 'Min' }
				        //   ]
				        // },
				      },
				      {
				        name: 'Lowest',
				        type: 'line',
				        data: [103, 101, 103, 103, 23, 22, 29],
						lineStyle:{
						color:'#6f9cef'
						},
				        // markPoint: {
				        //   data: [{ name: '周最低', value: -2, xAxis: 1, yAxis: -1.5 }]
				        // },
				      }
				    ]
				}
				      myChart.setOption(option);
				},
			},
		mounted() {
		  this.$nextTick(() => {
		    this.createChart();
		  });
		},
	  }  
</script>

<style>
	.div1{
		width: 215px;
		height: 80px;
		border: 1px solid #ece5e5;
		background-color: white;
		margin: auto;
	}
	.div1 >span{
		line-height: 80px;
	}
</style>