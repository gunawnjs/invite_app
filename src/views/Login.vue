<template>
  <div class="wrapper">
    <v-spacer />  
      <v-card flat elevation="24" class="login pa-12 rounded-lg">
        <v-card-title class="text-sm-center justify-center py-6" primary-title>            
          <h2 class="font-weight-light">Login</h2>
        </v-card-title>
        <v-card-subtitle class="text-sm-center justify-center py-4">
          <h3 class="font-weight-thin">Silahkan masuk menggunakan email</h3>
        </v-card-subtitle>
          <v-form
          ref="form"
          v-model="valid"
          lazy-validation
        >
        <v-window v-model="step">
          <v-window-item  :value="1">            
            <v-card-text>
              <div class="pt-16 my-8">
                <v-text-field
                  v-model="email"
                  :rules="emailRules"
                  label="E-mail"
                  outlined
                  required
                ></v-text-field>
                
                <v-text-field
                  v-model="password"
                  :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  :rules="passwordRules"
                  :type="showPassword ? 'text' : 'password'"
                  label="Password"
                  @click:append="showPassword = !showPassword"
                  outlined
                  required
                ></v-text-field>
                <v-btn
                  class="white--text"
                  :disabled="!valid"
                  color="light-blue darken-1"
                  @click="validate"
                  block
                  depressed
                >
                  Login
                </v-btn>
                <v-btn
                  color="primary"
                  class="py-5 mt-3"
                  @click="step++"
                  block
                  text
                  small
                >
                  Buat akun
                </v-btn>
              </div>
            </v-card-text>
          </v-window-item>

          <v-window-item  :value="2">            
            <v-card-text>
              <div>
                <v-text-field
                  v-model="nama"
                  :rules="namaRules"
                  label="Nama Lengkap"
                  outlined
                  required
                />
                <v-text-field
                  v-model="email"
                  :rules="emailRules"
                  label="E-mail"
                  outlined
                  required
                />           
                <v-text-field
                  v-model="password"
                  :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  :rules="passwordRules"
                  :type="showPassword ? 'text' : 'password'"
                  label="Password"
                  @click:append="showPassword = !showPassword"
                  outlined
                  required
                />
                <v-text-field
                  v-model="password"
                  :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  :rules="passwordRules"
                  :type="showPassword ? 'text' : 'password'"
                  label="Konfirmasi"
                  @click:append="showPassword = !showPassword"
                  outlined
                  required
                 />
                <v-btn
                  color="light-blue darken-1"
                  class="white--text py-5 mt-3"
                  @click="step--"
                  block
                  small
                  depressed
                >
                  Buat akun
                </v-btn>
              </div>
            </v-card-text>
          </v-window-item>
        </v-window>

        </v-form>
      </v-card>
    <v-spacer />
  </div>
</template>

<script>
  export default {
    data: () => ({
      step:1,
      valid: true,
      nama: '',
      namaRules: [
        v => !!v || 'Masukan nama lengkap !',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      email: '',
      emailRules: [
        v => !!v || 'Alamat surel anda belum terisi !',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      showPassword:false,
      password: '',
      passwordRules: [
        v => !!v || 'Password anda masih kosong !',
      ],
    }),

    methods: {
      validate () {
        this.$refs.form.validate()
      },
    },
  }
</script>

<style scoped>
.login{
  width: 100%;
  max-width: 30rem;
  margin: 0 auto;
}
</style>