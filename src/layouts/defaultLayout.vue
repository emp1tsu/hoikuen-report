<script setup lang="ts">
import { useRouter } from "vue-router";

const router = useRouter();

function onClick() {
  router.push("/monthly-reports/create");
}
</script>

<template>
  <v-app>
    <v-layout>
      <v-app-bar color="primary" title="保育園レポート"></v-app-bar>

      <v-main>
        <Suspense>
          <template #default>
            <RouterView />
          </template>
          <template #fallback>loading...</template>
        </Suspense>
      </v-main>
    </v-layout>

    <!-- <create-report /> -->
    <v-layout-item class="text-end" model-value position="bottom" size="88">
      <div class="ma-4">
        <v-fab-transition>
          <v-btn
            class="mt-auto"
            color="primary"
            icon="mdi-plus"
            size="large"
            @click="onClick"
          />
        </v-fab-transition>
      </div>
    </v-layout-item>
  </v-app>
</template>
