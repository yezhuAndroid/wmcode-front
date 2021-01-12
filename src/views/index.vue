<template>
  <div>
    <el-form ref="elForm" :model="formData" :rules="rules" size="medium" label-width="100px">
      <el-row gutter="15">
        <el-form-item label="发动机选择"  label-width="120px" prop="field108">
          <el-radio-group v-model="formData.field108" size="medium">
            <el-radio v-for="(item, index) in field108Options" :key="index" :label="item.value"
              :disabled="item.disabled">{{item.label}}</el-radio>
          </el-radio-group>
        </el-form-item>
        <el-form-item label="传动方式" label-width="120px" prop="field109">
          <el-radio-group v-model="formData.field109" size="medium">
            <el-radio v-for="(item, index) in field109Options" :key="index" :label="item.value"
              :disabled="item.disabled">{{item.label}}</el-radio>
          </el-radio-group>
        </el-form-item>
        <el-form-item label="吨位" label-width="120px" prop="field110">
          <el-radio-group v-model="formData.field110" size="medium">
            <el-radio v-for="(item, index) in field110Options" :key="index" :label="item.value"
              :disabled="item.disabled">{{item.label}}</el-radio>
          </el-radio-group>
        </el-form-item>

         <el-form-item label="轴距" prop="field103">
          <el-radio-group v-model="formData.field103" size="medium">
            <el-radio v-for="(item, index) in field103Options" :key="index" :label="item.value"
              :disabled="item.disabled">{{item.label}}</el-radio>
          </el-radio-group>
        </el-form-item>


      </el-row>
      <el-form-item size="large">
        <el-button type="primary" @click="submitForm">提交</el-button>
        <el-button @click="resetForm">重置</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  components: {},
  props: [],
  data() {
    return {
      formData: {
        field108: 1,
        field109: 1,
        field110: 1,
      },
      rules: {
        field108: [{
          required: true,
          message: '发动机选择不能为空',
          trigger: 'change'
        }],
        field109: [{
          required: true,
          message: '传动方式不能为空',
          trigger: 'change'
        }],
        field110: [{
          required: true,
          message: '吨位不能为空',
          trigger: 'change'
        }],
      },
      field108Options: [{
        "label": "康明斯",
        "value": 1
      }, {
        "label": "潍柴",
        "value": 2
      }],
      field109Options: [{
        "label": "液力传动",
        "value": 1
      }, {
        "label": "机械传动",
        "value": 2
      }, {
        "label": "静液压传动",
        "value": ""
      }, {
        "label": "电传动",
        "value": ""
      }],
      field110Options: [{
        "label": "2吨",
        "value": 2
      }, {
        "label": "3吨",
        "value": 3
      }, {
        "label": "5吨",
        "value": 5
      }, {
        "label": "6吨",
        "value": 6
      }, {
        "label": "7吨",
        "value": 7
      }, {
        "label": "8吨",
        "value": 8
      }, {
        "label": "9吨",
        "value": 9
      }, {
        "label": "12吨",
        "value": 12
      }, {
        "label": "13吨",
        "value": 13
      }, {
        "label": "14吨",
        "value": 14
      }, {
        "label": "15吨",
        "value": 15
      }],
      field103Options: [{
        "label": "短轴距_2",
        "value": 1
      }, {
        "label": "中轴距_3",
        "value": 2
      }, {
        "label": "中轴距_5",
        "value": ""
      }, {
        "label": "长轴距_6",
        "value": ""
      }, {
        "label": "长轴距_8",
        "value": ""
      }, {
        "label": "长轴距_9",
        "value": ""
      }]
    }
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {
    submitForm() {
      this.$refs['elForm'].validate(valid => {
        if (!valid) return
        // TODO 提交表单
      })
    },
    resetForm() {
      this.$refs['elForm'].resetFields()
    },
  }
}

</script>
<style>
</style>
