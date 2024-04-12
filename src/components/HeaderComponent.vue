<template>
    <q-header>
        <q-toolbar class="container justify-between">

            <div>
                <q-item clickable tag="a" target="_blank" :href="link">
                    <SiteLogo />
                </q-item>
            </div>

            <div class="row">
                <q-item clickable tag="a" target="_blank" :href="link">채용 <q-icon name="keyboard_arrow_down" />
                    <q-menu>
                        <q-list style="min-width: 100px">
                            <q-item clickable v-close-popup>
                                <q-item-section>채용</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                                <q-item-section>해외 개발자 원격 채용</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                                <q-item-section>외국인 원격 채용 (비개발 직군)</q-item-section>
                            </q-item>
                            <q-separator />
                            <q-item clickable v-close-popup>
                                <q-item-section>한국어 가능 외국인 채용</q-item-section>
                            </q-item>
                        </q-list>
                    </q-menu>
                </q-item>
                <q-item clickable tag="a" target="_blank" :href="link">해외 개발자 활용 서비스</q-item>
            </div>

            <div><q-btn color="white" text-color="black" label="문의하기" /></div>
        </q-toolbar>
    </q-header>
</template>

<script setup>
import { ref } from 'vue'
import SiteLogo from './SiteLogo.vue'

defineOptions({
    name: 'HeaderComponent'
})


</script>