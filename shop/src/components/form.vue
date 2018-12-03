 <element>
<el-form ref="form" :rules="rules" :model="form" label-width="300px">
        <el-form-item label="发货地址：" prop="fAdderss">
          <el-input class="inp" v-model="form.fAdderss" auto-complete="true"></el-input>
          <el-button type="primary" class="btn-add" >常用地址</el-button>
        </el-form-item>
     </el-form>
     <element/>
<script>
export default {
  data() {
    return {
      form: {
        fAdderss: '',
      },
      // 校验规则
      rules: {
        fAdderss: [
        { required: true, //是否必填
          message: '地址不能为空', //规则
          trigger: 'blur'  //何事件触发
        },
        //可以设置双重验证标准
        { min: 3, max: 5,  message: '长度在 3 到 5 个字符', }
      ]
      }
    }
  }
}
</script>
