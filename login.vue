<template>
  <div>
    <v-img
      class="mx-auto my-6"
      max-width="150"
      src="C:\xampp\htdocs\master2\img\3.png"
    ></v-img>

    <v-card
      class="mx-auto pa-12 pb-8"
      elevation="8"
      max-width="448"
      rounded="lg"
    >
      <!-- Account Title -->
  <div class="text-subtitle-1 text-medium-emphasis">อีเมล</div>

<!-- Email Input Field -->
<v-text-field
  v-model="email"
  density="compact"
  placeholder="อีเมล"
  prepend-inner-icon="mdi-email-outline"
  variant="outlined"
  aria-label="Email address"
</v-text-field>


       <!-- Password Section with 'Forgot Password' Link -->
  <div
    class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between mt-4"
  >
    รหัสผ่าน
    <a
      class="text-caption text-decoration-none text-blue"
      href="#"
      rel="noopener noreferrer"
      target="_blank"
    >
      ลืมรหัสผ่านในการเข้าสู่ระบบ?
    </a>
      </div>

      <v-text-field
        v-model="password"
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        placeholder="รหัสผ่าน"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <!-- <v-card class="mb-12" color="surface-variant" variant="tonal">
        <v-card-text class="text-medium-emphasis text-caption">
          Warning: After 3 consecutive failed login attempts, you account will
          be temporarily locked for three hours. If you must login now, you can
          also click "Forgot login password?" below to reset the login password.
        </v-card-text>
      </v-card> -->

      <v-btn @click="doLogin" class="mb-8" color="blue" size="large" variant="tonal" block>
        เข้าสู่ระบบ
      </v-btn>

      <v-card-text class="text-center">
        <a
          class="text-blue text-decoration-none"
          href="#"
          rel="noopener noreferrer"
          target="_blank"
        >

        </a>
      </v-card-text>
    </v-card>
  </div>
</template>
<script>
definePageMeta({
  layout: "custom",
});
  import axios from 'axios';
export default {

  data: () => ({
    visible: false,
    email: "",
    password: ""
  }),
  methods: {
    async doLogin() {
      this.$router.replace('/datatable')
      let forms = {
      email: this.email,
      password: this.password
    }  
    console.log(this.email)
    console.log(forms.password)
    console.log(forms)
    const res = await axios.post('http://localhost:7000/login', forms)
    const data = await res.data
    console.log(data.status)
    if (data.status == 'success') {
      console.log(data.row.email)
      // window.sessionStorage.setItem("user", JSON.stringify(data.row.email)); // แบบนี้หาย เมื่อ restart หรือ ปิด  browser
      window.sessionStorage.setItem("token", JSON.stringify(data.token));
      this.$router.replace('/datatable')

    }else{
      this.$router.replace('/login')
    }
  }
  }
};
</script>