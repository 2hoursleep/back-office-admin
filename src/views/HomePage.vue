<!--
  Copyright D3 Ledger, Inc. All Rights Reserved.
  SPDX-License-Identifier: Apache-2.0
-->
<template>
  <el-container>
    <Menu />
    <el-main style="width: 100%; height: 100vh; padding: 0; padding-left: 62px;">
      <router-view />
    </el-main>
    <confirm-modal />
    <registration-modal />
  </el-container>
</template>

<script>
import { lazyComponent } from '@router'

export default {
  name: 'home-page',
  components: {
    Menu: lazyComponent('Home/Menu'),
    ConfirmModal: lazyComponent('common/modals/ConfirmModal'),
    RegistrationModal: lazyComponent('common/modals/RegistrationModal')
  },
  data () {
    return {}
  }
}
</script>

<style>

.item__private-keys {
  width: 40px;
  height: 40px;
  border-radius: 24px;
  border: solid 1px #cccccc;
  display: flex;
  justify-content: center;
}

.item__private-keys-success {
  border: solid 1px #67c23a;
}

/* in order not to make a border green when a private key is empty */
.el-form-item.is-success .el-input.is-empty .el-input__inner {
  border-color: #dcdfe6;
}
.approval_form-desc {
  text-align: center;
}

.approval_form-item-clearm {
  margin: 0;
}

.approval_form .el-input__inner {
  background-color: #ffffff;
  color: #000000;
  border: solid 1px rgba(0, 0, 0, 0.2);
  font-weight: 700;
  height: 4.5rem;
  padding-left: 1.2rem;
  padding-top: 1.2rem;
  line-height: 0;
  font-size: 1rem;
}

.approval_form .el-form-item__label {
  line-height: 1;
  position: relative;
  top: 2rem;
  z-index: 10;
  margin-left: 1.2rem;
  font-size: 0.8rem;
  opacity: 0.56;
  color: #000000;
}
.approval_form-upload .el-button,
.approval_form-upload .el-button:focus {
  width: 3.8rem;
  height: 4.5rem;
  border: solid 1px rgba(0, 0, 0, 0.2);
  background-color: #ffffff;
  color: rgba(0, 0, 0, 0.2);
  padding: 0;
  font-size: 1.2rem;
  border-radius: 0.3rem;
}

.approval_form-upload .el-button:hover {
  border-color: #000000;
  color: #000000;
}

.approval_form-counter {
  margin-top: 1rem;
}

.dialog-form_buttons-block {
  display: flex;
  justify-content: space-between;
}
.dialog-form_buttons {
  height: 3.5rem;
  width: 13.5rem;
  text-transform: uppercase;
  font-size: 0.8rem;
}
.dialog-form_buttons.action {
  background-color: #041820;
  color: #ffffff;
  border: 1px solid #041820;
}
.dialog-form_buttons.action.is-disabled {
  opacity: 0.8;
}
.dialog-form_buttons.action:hover {
  background-color: #041820;
}
.dialog-form_buttons.close {
  color: #000000;
  border: 1px solid #1d1f20;
}
.dialog-form_buttons.close:hover {
  background-color: rgba(0, 0, 0, 0.025);
}
</style>

<style scoped>
.exchange_form >>> .el-form-item__label::before,
.approval_form >>> .el-form-item__label::before {
  content: '';
}
</style>
