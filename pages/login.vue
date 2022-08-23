<template>
  <div class="page--auth">
    <div class="main--wrapper">
      <div class="auth--block-parent">
        <div class="auth--block">
          <div class="auth--block-wrapper">
            <div class="auth--block-title">Spublup</div>
            <div class="auth--block-text">
              Что бы воспользоваться ботом требуется авторизация через
              стриминговый сервис <span class="purple">Twitch</span>
            </div>
            <div class="auth--block-submit tmiAuth" @click="userLogin()">Авторизация</div>
          </div>
        </div>

        <img src="~/assets/img/auth-fly-top.svg" alt="" class="image--fly image--fly-top"/>
        <img src="~/assets/img/auth-fly-bottom.png" alt="" class="image--fly image--fly-bottom"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'auth',
  name: "login.vue",
  methods:{
    userLogin() {
      this.$auth.loginWith('twitch')
    }
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@200;400;600;700;800;900&display=swap");


html *,
body * {
  font-family: "Inter";
}

.main--wrapper {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.auth--block-parent {
  position: relative;
  width: -webkit-fit-content;
  width: -moz-fit-content;
  width: fit-content;
  height: -webkit-fit-content;
  height: -moz-fit-content;
  height: fit-content;
  transition: all 0.4s cubic-bezier(0.075, 0.82, 0.165, 1);
  transition-property: transform;
}

.auth--block-parent .image--fly {
  position: absolute;
  z-index: 1;
  transition: all 1s cubic-bezier(0.63, -0.1, 0.36, 1.21);
  transition-property: left right transform;
}

.auth--block-parent .image--fly-top {
  top: -46px;
  left: -66px;
  transform: scale(0.92);
}

.auth--block-parent .image--fly-bottom {
  width: 216px;
  height: 216px;
  right: 0;
  bottom: 0;
  transform: scale(0.92);
}

.auth--block-parent:hover {
  transform: translateY(-10px);
}

.auth--block-parent:hover .image--fly-top {
  top: -70px;
  left: -70px;
  transform: scale(1) rotateZ(10deg);
}

.auth--block-parent:hover .image--fly-bottom {
  right: -140px;
  bottom: -20px;
  transform: scale(1.2) rotateZ(-20deg);
}

.auth--block-wrapper {
  position: relative;
  z-index: 2;
  padding: 24px 24px 42px 24px;
  text-align: center;
  background: #0e0f10;
  border-radius: 10px;
  border: 1px solid #000000;
  width: 358px;
  height: -webkit-fit-content;
  height: -moz-fit-content;
  height: fit-content;
  width: 358px;
  height: fit-content;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.auth--block-title {
  margin-bottom: 24px;
  font-size: 24px;
  font-weight: 900;
  background: linear-gradient(93.39deg, #3c1a9d -11.01%, #dd2ad6 99.88%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.auth--block-text {
  margin-bottom: 42px;
  font-size: 16px;
  font-weight: 400;
  line-height: 19px;
  color: #6f6f6f;
}

.auth--block-text .purple {
  font-weight: 700;
  color: #9146ff;
}

.auth--block-submit {
  padding: 8px 16px;
  font-size: 18px;
  font-weight: 700;
  color: #000;
  background: #edfe2f;
  border-radius: 6px;
  box-sizing: border-box;
  cursor: pointer;
  width: 100%;
  height: auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  transition: all 0.4s cubic-bezier(0.075, 0.82, 0.165, 1);
}

.auth--block-submit:hover {
  transform: translateY(-4px);
}
</style>
