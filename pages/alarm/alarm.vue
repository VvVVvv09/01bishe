<template>
	<view >
		<div style="text-align: center;">
			<el-select v-model="value" placeholder="请选择" size="medium" style="height: 90px; text-align: center;">
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
				  value: '0',
				  label: '紧急事件'
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
				value: '0'
			}
		},
		methods: {
			createChart() {
				      var myChart =this.$echarts.init(document.getElementById('chart'))
				      let option = {
						 // title: {
						 //    text: 'Basic Radar Chart'
						 //  },
						  // legend: {
						  //   data: ['Allocated Budget', 'Actual Spending']
						  // },
						  radar: {
						    // shape: 'circle',
						    indicator: [
						      { name: '转速', max: 6500 },
						      { name: '温度', max: 16000 },
						      { name: '压强', max: 30000 },
						      { name: '湿度', max: 38000 },
						      { name: '扭矩', max: 52000 },
						    ]
						  },
						  series: [
						    {
						      name: 'leida',
						      type: 'radar',
						      data: [
						        {
						          value: [4200, 3000, 20000, 35000, 50000, 18000],
						          name: 'Allocated Budget'
						        },
						        {
						          value: [5000, 14000, 28000, 26000, 42000, 21000],
						          name: 'Actual Spending'
						        }
						      ]
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
		}
	}
</script>

<style scoped>
	/deep/.el-input--medium .el-input__inner {
	    height: 90px;
	    line-height: 36px;
		text-align: center;
	}
</style>
