<template>
  <div class="adv-apps-wrapper">
    <h2>应用管理</h2>
    <div class="apps-top-wrapper clearfix">
      <div class="apps-search pull-right">
        <el-input placeholder="请输入内容"></el-input>
        <el-button type="primary">搜索</el-button>
      </div>
    </div>
    <div class="apps-data-table">
      <el-table :data="tableData5" style="width: 100%">
        <el-table-column type="expand">
          <template scope="props">
            <el-form label-position="left" inline class="demo-table-expand sub-app-form">
              <el-form-item label="提交时间:">
                <span>{{ props.row.time }}</span>
              </el-form-item>
              <el-form-item label="广告类型:">
                <span>{{ props.row.shop }}</span>
              </el-form-item>
              <el-form-item label="广告位ID:">
                <span>{{ props.row.id }}</span>
              </el-form-item>
              <el-form-item label="广告位名称:" title="广告位名称">
                <span>{{ props.row.shopId }}</span>
              </el-form-item>
              <el-form-item label="分成/固定单价:" title="分成/固定单价">
                <span>{{ props.row.category }}</span>
              </el-form-item>
              <el-form-item label="操作:">
                <template scope="scope">
                  <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">API源</el-button>
                  <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">SDK源</el-button>
                  <el-button size="small" type="info" @click="handleDelete(scope.$index, scope.row)">频次</el-button>
                  <el-button size="small" type="info" @click="handleDelete(scope.$index, scope.row)">分成</el-button>
                </template>
              </el-form-item>
            </el-form>
            <el-form label-position="left" inline class="demo-table-expand sub-app-form">
              <el-form-item label="提交时间:">
                <span>{{ props.row.time }}</span>
              </el-form-item>
              <el-form-item label="广告类型:">
                <span>{{ props.row.shop }}</span>
              </el-form-item>
              <el-form-item label="广告位ID:">
                <span>{{ props.row.id }}</span>
              </el-form-item>
              <el-form-item label="广告位名称:" title="广告位名称">
                <span>{{ props.row.shopId }}</span>
              </el-form-item>
              <el-form-item label="分成/固定单价:" title="分成/固定单价">
                <span>{{ props.row.category }}</span>
              </el-form-item>
              <el-form-item label="操作:">
                <template scope="scope">
                  <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">API源</el-button>
                  <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">SDK源</el-button>
                  <el-button size="small" type="info" @click="handleDelete(scope.$index, scope.row)">频次</el-button>
                  <el-button size="small" type="info" @click="handleDelete(scope.$index, scope.row)">分成</el-button>
                </template>
              </el-form-item>
            </el-form>
            <el-form label-position="left" inline class="demo-table-expand sub-app-form">
              <el-form-item label="提交时间:">
                <span>{{ props.row.time }}</span>
              </el-form-item>
              <el-form-item label="广告类型:">
                <span>{{ props.row.shop }}</span>
              </el-form-item>
              <el-form-item label="广告位ID:">
                <span>{{ props.row.id }}</span>
              </el-form-item>
              <el-form-item label="广告位名称:" title="广告位名称">
                <span>{{ props.row.shopId }}</span>
              </el-form-item>
              <el-form-item label="分成/固定单价:" title="分成/固定单价">
                <span>{{ props.row.category }}</span>
              </el-form-item>
              <el-form-item label="操作:">
                <template scope="scope">
                  <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">API源</el-button>
                  <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">SDK源</el-button>
                  <el-button size="small" type="info" @click="handleDelete(scope.$index, scope.row)">频次</el-button>
                  <el-button size="small" type="info" @click="handleDelete(scope.$index, scope.row)">分成</el-button>
                </template>
              </el-form-item>
            </el-form>
          </template>
        </el-table-column>
        <el-table-column label="提交时间" prop="time"></el-table-column>
        <el-table-column label="公司名称" prop="name"></el-table-column>
        <el-table-column label="应用ID" prop="appid"></el-table-column>
        <el-table-column label="应用名称" prop="appname"></el-table-column>
        <el-table-column label="操作系统" prop="os"></el-table-column>
        <el-table-column label="分成/固定单价" prop="price"></el-table-column>
        <el-table-column label="平台/外放">
          <template scope="scope">
            <el-select v-model="value" placeholder="请选择">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
          </template>
        </el-table-column>
        <el-table-column label="应用下载">
          <template scope="scope">
            <el-button type="info" size="small" @click="handleEdit(scope.$index, scope.row)">下载</el-button>
          </template>
        </el-table-column>
        <el-table-column label="审核状态" prop="state"></el-table-column>
        <el-table-column label="投放状态" prop="state1"></el-table-column>
        <el-table-column label="审核">
          <template scope="scope">
            <el-button type="success" size="small" @click="handleEdit(scope.$index, scope.row)">通过</el-button>
            <el-button type="danger" size="small" @click="handleEdit(scope.$index, scope.row)">拒绝</el-button>
          </template>
        </el-table-column>
        <el-table-column label="操作">
          <template scope="scope">
            <el-button type="info" size="small" @click="configur(scope.$index, scope.row)">分成</el-button>
            <el-switch v-model="value2" on-color="#13ce66" off-color="#ff4949"></el-switch>
          </template>
        </el-table-column>
      </el-table>
    </div>
    <div class="pager-wrapper clearfix">
      <pager :total-records="totalRecords" :page-sizes="pageSize" :page-nums="pageNum"></pager>
    </div>
  </div>
</template>

<script type="ecmascript-6">
import pager from '../../../components/pager/pager.vue';
export default {
  data () {
    return {
      tableData5: [{
          id: '12987122',
          time: '2017-03-06',
          category: '江浙小吃、小吃零食',
          address: '上海市普陀区真北路',
          shop: '王小虎夫妻店',
          shopId: '10333',
          name: '大发有限',
          os: 'android',
          appid: '12',
          appname: '今日头条',
          price: '70%',
          state: '通过',
          state1: '通过'
        }, {
          id: '12987123',
          time: '2017-03-06',
          category: '江浙小吃、小吃零食',
          address: '上海市普陀区真北路',
          shop: '王小虎夫妻店',
          shopId: '10333',
          name: '大发有限',
          os: 'android',
          appid: '12',
          appname: '今日头条',
          price: '70%',
          state: '通过',
          state1: '通过'
        }, {
          id: '12987125',
          time: '2017-03-06',
          category: '江浙小吃、小吃零食',
          address: '上海市普陀区真北路',
          shop: '王小虎夫妻店',
          shopId: '10333',
          name: '大发有限',
          os: 'android',
          appid: '12',
          appname: '今日头条',
          price: '70%',
          state: '通过',
          state1: '通过'
        }, {
          id: '12987126',
          time: '2017-03-06',
          category: '江浙小吃、小吃零食',
          address: '上海市普陀区真北路',
          shop: '王小虎夫妻店',
          shopId: '10333',
          name: '大发有限',
          os: 'android',
          appid: '12',
          appname: '今日头条',
          price: '70%',
          state: '通过',
          state1: '通过'
        }],
        totalRecords: 100,
        pageNum: 1,
        pageSize: 10,
        options: [{
          value: '选项1',
          label: '平台'
        }, {
          value: '选项2',
          label: '外放'
        }],
        value: '',
        value2: true
    };
  },
  components: { pager },
  methods: {
    handleEdit (index, row) {
      console.log(index, row);
    },
    handleDelete (index, row) {
      console.log(index, row);
    },
    configur () {
      this.$router.push({path: 'app/configur',query: {plan: '123'}});
    }
  }
};
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .adv-apps-wrapper
    overflow: hidden
    .apps-top-wrapper
      margin-bottom: 15px
      .apps-search
        max-width: 300px
        font-size: 0
        .el-input
          width: 230px
          input
            border-radius: 4px 0 0 4px
        button 
          border-radius: 0 4px 4px 0
    .apps-data-table
      font-size: 0
      .el-select
        width: 90px
        .el-input__inner
          height: 28px
      .sub-app-form
        padding: 10px
        border-bottom: 1px dashed #bbb
        label
          width: 75px
          overflow: hidden
          white-space: nowrap
          text-overflow: ellipsis
          color: #99a9bf
        .el-form-item
          margin-right: 0
          margin-bottom: 0
          width: 48%  
      .sub-app-form:last-child
        border: none           
    .pager-wrapper
      margin-top: 15px      
</style>
