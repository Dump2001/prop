<template>
  <v-app>
    <v-app-bar app color="teal" dark>
      <div class="d-flex align-center" to="/">
        <v-img alt="Vuetify Logo" class="shrink mr-2" contain
        src="https://mahidol.ac.th/temp/2019/06/logo-MU_Color.png"
        transition="scale-transition" width="60" />
      </div>

      <v-spacer></v-spacer>

      <v-btn to="/" text>
        <span class="mr-2">Home</span>
      </v-btn>
      <v-btn to="/todo" text>
        <span class="mr-2">ลงทะเบียน</span>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
