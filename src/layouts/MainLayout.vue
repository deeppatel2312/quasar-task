<template>
  <q-layout view="lHh Lpr lFf">
    <HeaderComponent />

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import HeaderComponent from 'components/HeaderComponent.vue'

defineOptions({
  name: 'MainLayout'
})

</script>
