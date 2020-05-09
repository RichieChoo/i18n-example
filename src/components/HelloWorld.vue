<template>
	<div class="hello">
		<el-form style="width:45%;" ref="form" :model="form" label-width="80px">
			<div>
				我 我我 你 你你
				你你你
				他他他
			</div>
			<div>你好<span>张三</span>先生
			</div>
			<el-form-item label="活动名称">
				<el-input v-model="form.name"></el-input>
			</el-form-item>
			<el-form-item label="活动区域">
				<el-select v-model="form.region" placeholder="请选择活动区域">
					<el-option label="区域一" value="shanghai"></el-option>
					<el-option label="区域二" value="beijing"></el-option>
				</el-select>
			</el-form-item>
			<el-form-item label="活动时间">
				<el-col :span="11">
					<el-date-picker type="date" placeholder="选择日期" v-model="form.date1" style="width: 100%;"></el-date-picker>
				</el-col>
				<el-col class="line" :span="2">-</el-col>
				<el-col :span="11">
					<el-time-picker placeholder="选择时间" v-model="form.date2" style="width: 100%;"></el-time-picker>
				</el-col>
			</el-form-item>
			<el-form-item label="即时配送">
				<el-switch v-model="form.delivery"></el-switch>
			</el-form-item>
			<el-form-item label="活动性质">
				<el-checkbox-group v-model="form.type">
					<el-checkbox label="美食/餐厅线上活动" name="type"></el-checkbox>
					<el-checkbox label="地推活动" name="type"></el-checkbox>
					<el-checkbox label="线下主题活动" name="type"></el-checkbox>
					<el-checkbox label="单纯品牌曝光" name="type"></el-checkbox>
				</el-checkbox-group>
			</el-form-item>
			<el-form-item label="特殊资源">
				<el-radio-group v-model="form.resource">
					<el-radio label="线上品牌商赞助"></el-radio>
					<el-radio label="线下场地免费"></el-radio>
				</el-radio-group>
			</el-form-item>
			<el-form-item label="活动形式">
				<el-input type="textarea" v-model="form.desc"></el-input>
			</el-form-item>
			<el-form-item>
				<el-button type="primary" @click="onSubmit">立即创建</el-button>
				<el-button>取消</el-button>
			</el-form-item>
		</el-form>

		<el-table :data="tableData" style="width: 45%">
			<el-table-column prop="date" label="日期" width="150"></el-table-column>
			<el-table-column label="配送信息">
				<el-table-column prop="name" label="姓名" width="120"></el-table-column>
				<el-table-column label="地址">
					<el-table-column prop="province" label="省份" width="120"></el-table-column>
					<el-table-column prop="city" label="市区" width="120"></el-table-column>
					<el-table-column prop="address" label="地址" width="300"></el-table-column>
					<el-table-column prop="zip" label="邮编" width="120"></el-table-column>
				</el-table-column>
			</el-table-column>
		</el-table>
	</div>
</template>
<script>
export default {
	name: "HelloWorld",
	props: {
		msg: String
	},
	data() {
		return {
			form: {
				name: "",
				region: "",
				date1: "",
				date2: "",
				delivery: false,
				type: [],
				resource: "",
				desc: ""
			},
			tableData: [
				{
					date: "2016-05-03",
					name: "王小虎1",
					province: "上海",
					city: "普陀区",
					address:
						"上" +
						"海" +
						"市" +
						"普" +
						"陀" +
						"区" +
						"金" +
						"沙" +
						"江" +
						"路1518弄",
					zip: 200333
				},
				{
					date: "2016-05-02",
					name: "王小虎2",
					province: "上海",
					city: "普陀区",
					address: "上海市普陀区金沙江路1518弄",
					zip: 200333
				},
				{
					date: "2016-05-04",
					name: "王小虎3",
					province: "上海",
					city: "普陀区",
					address: "上海市普陀区金沙江路1518弄",
					zip: 200333
				},
				{
					date: "2016-05-01",
					name: "王小虎4",
					province: "上海",
					city: "普陀区",
					address: "上海市普陀区金沙江路1518弄",
					zip: 200333
				},
				{
					date: "2016-05-08",
					name: "王小虎5",
					province: "上海",
					city: "普陀区",
					address: "上海市普陀区金沙江路1522弄",
					zip: 200333
				},
				{
					date: "2016-05-06",
					name: "王小虎6",
					province: "上海",
					city: "普陀区",
					address: "上海市普陀区金沙江路1518弄",
					zip: 200333
				},
				{
					date: "2016-05-07",
					name: "王小虎7",
					province: "上海",
					city: "普陀区",
					address: "上海市普陀区金沙江路1518弄",
					zip: 200333
				}
			]
		};
	},
	methods: {
		onSubmit() {
			console.log("submit!");
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="less" scoped>
.hello {
	display: flex;
	justify-content: space-between;
	height: 500px;
}
</style>
