<template>
  <mainBase>
    <div class="account" slot="data_items">
      <div class="account_info">
        <form class="form-horizontal">
          <div class="form-group">
            <div class="head">
              <div class="img">
                <div class="wrapper">修改头像</div>
                <img src="../../assets/img/test2.jpg" alt />
              </div>
            </div>
          </div>
          <div class="form-group">
            <label for="accout_id" class="col-push-2 col-sm-2 control-label">ID</label>
            <div class="col-sm-6">
              <input type="text" class="form-control" id="account_id" readonly />
            </div>
          </div>
          <div class="form-group">
            <label for="account_name" class="col-sm-2 control-label"
              >用户名</label
            >
            <div class="col-sm-6">
              <input type="text" class="form-control" id="account_name" />
            </div>
          </div>
          <div class="form-group">
            <label for="real_name" class="col-sm-2 control-label"
              >真实姓名</label
            >
            <div class="col-sm-6">
              <input type="text" class="form-control" id="real_name" />
            </div>
          </div>
          <div class="form-group">
            <label for="account_email" class="col-sm-2 control-label"
              >Email</label
            >
            <div class="col-sm-6">
              <input type="email" class="form-control" id="account_email" />
            </div>
          </div>
          <div class="form-group">
            <label for="department" class="col-sm-2 control-label">所属部门</label>
            <div class="col-sm-6">
              <input type="text" class="form-control" id="department" />
            </div>
          </div>
          <div class="actions">
            <button class="btn btn-primary">确认修改</button>
            <a data-toggle="modal" :data-target="'#'+myModel" class="btn btn-danger">修改密码</a>
          </div>
          <modal :myModal='myModel'>
            <span slot="modal-name">修改密码</span>
            <changePw slot="modal-body"></changePw>
          </modal>
        </form>
      </div>
    </div>
  </mainBase>
</template>

<script>
import mainBase from "../../components/main/mainBase"
import modal from "../../components/common/modal"
import changePw from "./childrenAccount/changePw"
export default {
  name: "account",
  data(){
    return {
      myModel: 'changePw'
    }
  },
  components: {
    mainBase,
    modal,
    changePw
  },
};
</script>
<style scoped>
.head .img {
  width: 200px;
  height: 200px;
  margin-left: 40%;
  transform: translateX(-50%);
  /* margin-left: -20px; */
  margin-top: 50px;
  margin-bottom: 20px;
  overflow: hidden;
  border-radius: 50%;
  cursor: pointer;
}
.head .img .wrapper {
  display: none;
  width: 100%;
  height: 100%;
  text-align: center;
  line-height: 200px;
  position: absolute;
  top: 0;
  left: 0;
  color: #fff;
  font-size: 30px;
  background-color: rgba(0, 0, 0, 0.3)
}
.head .img:hover .wrapper{
  display: block;
  
} 
.head .img img{
  width: 100%;
  height: 100%;
}
.head .img:hover .wrapper {
  display: block;
}
.head .img img {
  width: 100%;
  height: 100%;
}
.actions{
  margin: 15px 0;
  margin-left: 55%;
  transform: translateX(-50%);
}

.actions button:first-child{
  margin-right: 20px;
}
</style>