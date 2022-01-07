<template>
  <div class="home">
    <div class="login-box">
      <n-form
        :label-width="80"
        label-placement="left"
        :model="formValue"
        :size="size"
        ref="formRef"
      >
        <n-form-item label="用户名" path="user.name">
          <n-input class="form-item" placeholder="用户名" />
        </n-form-item>
        <n-form-item label="密码" path="user.age">
          <n-input
            class="form-item"
            placeholder="密码"
            v-model:value="formValue.user.age"
          />
        </n-form-item>
        <n-form-item>
          <n-button
            type="info"
            class="form-item btn"
            @click="handleValidateClick"
            attr-type="button"
            >登录</n-button
          >
          <n-button
            strong
            secondary
            type="info"
            class="form-item btn"
            @click="handleValidateClick"
            attr-type="button"
            >注册</n-button
          >
        </n-form-item>
      </n-form>
    </div>
  </div>
</template>

<script lang="ts">
// import { Options, Vue } from "vue-class-component";
// import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

// @Options({
//   components: {
//     // HelloWorld,
//   },
// })
// export default class Home extends Vue {}
import { defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    return {
      formValue: ref({
        user: {
          name: "",
          age: "",
        },
        phone: "",
      }),
    };
  },
});
</script>
<style scoped>
.home {
  display: flex;
  justify-content: center;
  /* align-items: center; */
}
.login-box {
  /* width: 500px; */
  height: 400px;
  margin-top: 200px;
}
.form-item {
  margin: 10px;
}
.btn {
  width: 100%;
}
</style>
