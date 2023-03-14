<template>
	<view>
	<button type="default" @click="changeTabBar" size="mini">111</button>
	<div class="chart" id="chart" style="height: 500px"></div>
	<div>
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
				        },]
			}
		},
		methods: {
			changeTabBar(){
				console.log(111);
				uni.navigateTo({
					url:'/pages/data/wrin'
				})
			},
			a(){
				 this.$router.push('wrin');
			},
			createChart() {
			      var myChart =this.$echarts.init(document.getElementById('chart'))
			      let option = {
			    // x轴
			    xAxis: {
			        // 一般情况 x轴都是 category
			        type: 'category',
			        data: ['转速', '温度', '压强', '扭矩', '温度']
			    },
			    // y 轴
			    yAxis: {
			        // 一般情况y轴也都是value型，数据来自series
			        type: 'value'
			    },
			    // 整个区域
			    series: [
			      {
			        name: 'Highest',
			        type: 'line',
			        data: [10, 11, 13, 11, 12, 12, 9],
			        markPoint: {
			          data: [
			            { type: 'max', name: 'Max' },
			            { type: 'min', name: 'Min' }
			          ]
			        },
			        // markLine: {
			        //   data: [{ type: 'average', name: 'Avg' }]
			        // }
			      },
			      {
			        name: 'Lowest',
			        type: 'line',
			        data: [1, -2, 2, 5, 3, 2, 0],
			        markPoint: {
			          data: [{ name: '周最低', value: -2, xAxis: 1, yAxis: -1.5 }]
			        },
			        // markLine: {
			        //   data: [
			        //     { type: 'average', name: 'Avg' },
			        //     [
			        //       {
			        //         symbol: 'none',
			        //         x: '90%',
			        //         yAxis: 'max'
			        //       },
			        //       {
			        //         symbol: 'circle',
			        //         label: {
			        //           position: 'start',
			        //           formatter: 'Max'
			        //         },
			        //         type: 'max',
			        //         name: '最高点'
			        //       }
			        //     ]
			        //   ]
			        // }
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

</style>
