<template>
  <v-sheet>
    <v-card
      class="mx-auto pa-12 pb-8"
      max-width="480"
      rounded="lg">
      <v-container fluid>
        <v-form
          v-model="form"
          @submit.prevent="login">
          <div class="text-subtitle-1 text-medium-emphasis">
            아이디
          </div>

          <v-text-field
            v-model="id"
            variant="outlined"
            density="compact"
            placeholder="아이디 입력" />
          
          <div class="text-subtitle-1 text-medium-emphasis">
            패스워드
          </div>

          <v-text-field
            v-model="password"
            :type="'password'"
            variant="outlined"
            density="compact"
            @click:append-inner="visible = !visible"
            placeholder="패스워드 입력" />

          <v-checkbox
            v-model="terms"
            color="secondary"
            label="아이디 저장" />

          <br />
          <br />

          <v-btn
            block
            color="success"
            size="large"
            type="submit"
            variant="elevated"
            @click="login();">
            로그인
          </v-btn>
        </v-form>
      </v-container>
    </v-card>
  </v-sheet>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      id: null,
      password: null,
      terms: false
    }
  },
  methods:{
    login(){
      this.$router.push({ name: 'Schedule' })
    }
  }
}
</script>

<style lang="scss">

.v-sheet {
    height: 428px;
    width: 380px;
    margin: 0 auto;
    position: absolute;
    top:50%;
    transform: translateY(-50%); 
    left:0;
    right: 0;
}
</style>