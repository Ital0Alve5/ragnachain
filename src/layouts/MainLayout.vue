<template>
  <q-layout view="hHh lpR fff">
    <q-header reveal bordered class="bg-dark text-white">
      <q-toolbar>
        <q-toolbar-title>
          <!-- <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar> -->
          Ragnachain
        </q-toolbar-title>
        <q-btn
          flat
          @click="drawerRight = !drawerRight"
          round
          dense
          icon="menu"
          class="mobile-only"
        />
        <q-btn-group outline class="desktop-only">
          <q-btn
            :to="{ path: btn.label.toLowerCase() }"
            :label="btn.label"
            :icon="btn.icon"
            v-for="btn in buttons"
            :key="btn.label"
          />
        </q-btn-group>
      </q-toolbar>
    </q-header>
    <q-drawer
      side="right"
      v-model="drawerRight"
      bordered
      :width="300"
      :breakpoint="1000"
      class="bg-dark"
      elevated
    >
      <q-scroll-area class="fit">
        <div class="q-pa-sm">
          <q-btn
            :to="{ path: btn.label.toLowerCase() }"
            :label="btn.label"
            :icon="btn.icon"
            v-for="btn in buttons"
            :key="btn.label"
            class="full-width q-mt-md"
          />
        </div>
      </q-scroll-area>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",
  data() {
    return {
      buttons: [
        {
          label: "Home",
          icon: "home",
        },
        {
          label: "Server",
          icon: "dns",
        },
        {
          label: "Download",
          icon: "download",
        },
        {
          label: "Currency",
          icon: "paid",
        },
        {
          label: "Register/Login",
          icon: "login",
        },
      ],
    };
  },
  setup() {
    return {
      drawerRight: ref(false),
    };
  },
});
</script>

<style scoped>
a[href="/login"] {
  background: white;
  color: #000;
}
</style>
