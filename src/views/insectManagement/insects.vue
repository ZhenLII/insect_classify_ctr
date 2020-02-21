<template>
  <div class="containner">
    <el-row type="flex" justify="start">
      <el-col :span="6" :offset="2">
        <span class="">昆虫信息</span>
      </el-col>
    </el-row>
    <el-row type="flex" justify="center">
      <el-col :span="20">
        <el-divider />
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="6" :offset="2">
        <el-input
          v-model="query"
          @change="handleSearchChange"
        />
      </el-col>
    </el-row>
    <el-row style="margin-top: 1%">
      <el-col :span="20" :offset="2">
        <el-table
          :data="insects"
          stripe
          border
          fit
          highlight-current-row
        >
          <el-table-column
            align="center"
            prop="insectId"
            label="昆虫id"
          />
          <el-table-column
            align="center"
            prop="insectName"
            label="昆虫名"
          />
          <el-table-column
            align="center"
            prop="scientificName"
            label="别名"
          />
          <el-table-column
            align="center"
            prop="insectAlias"
            label="学名"
          />
          <el-table-column
            align="center"
            prop="order"
            label="目"
          />
          <el-table-column
            align="center"
            prop="family"
            label="科"
          />
          <el-table-column
            align="center"
            prop="genus"
            label="属"
          />
          <el-table-column
            align="center"
            prop="description"
            label="介绍"
          />
          <el-table-column
            align="center"
            prop="feature"
            label="特征"
          />
          <el-table-column
            align="center"
            label="图片"
          />
        </el-table>
      </el-col>
    </el-row>
    <el-row type="flex" justify="center">
      <el-col :span="12" />
      <el-pagination
        :total="total"
        :current-page="currentPage"
        :page-sizes="[5, 10, 15, 20]"
        :page-size="pageSize"
        layout="total, sizes, prev, pager, next"
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
      />
      <el-col :span="2" />
    </el-row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      insects: [],
      query: '',
      total: 1,
      currentPage: 1,
      pageSize: 10
    }
  },
  methods: {
    handleCurrentChange: () => {},
    handleSizeChange: () => {},
    handleSearchChange: () => {}
  }
}
</script>
<style>
  span {
    font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    font-weight: bolder
  }
  .containner{
    align-content: center;
    margin-top: 2%;
  }
</style>
