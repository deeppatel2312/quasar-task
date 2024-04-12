<template>
    <div class="hero-banner-wrapper">
        <div class="container">
            <div class="row flex-center">
                <div class="col-lg-6">
                    <!-- Main text content -->
                    <h1>최고의 실력을 가진 외국인 인재를 찾고 계신가요?</h1>
                    <h4>법률 및 인사관리 부담없이 1주일 이내에 원격으로 채용해보세요.</h4>
                    <h6>개발자가 필요하신가요?</h6>

                    <!-- Iterate through TEXT_DATA and display text content -->
                    <div class="row">
                        <div class="col-lg-4" v-for="text in TEXT_DATA" :key="text.title">
                            <div class="text-wrap">
                                <h6>{{ text.title }}</h6>
                                <p>{{ text.description }}</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Empty column -->
                <div class="col-lg-6">
                    <div class="firstSlider">
                        <Carousel :items-to-show="2.5" :itemsToScroll="1" :wrap-around="true">
                            <Slide v-for="slide in 10" :key="slide">
                                <div class="carousel__item">
                                    <!-- {{ slide }} -->
                                    <img src="../assets/SliderImage.png" />
                                </div>
                            </Slide>

                            <template #addons>
                                <Navigation />
                            </template>
                        </Carousel>
                    </div>
                </div>

                <div class="col-lg-12">
                    <div class="secondSlider">
                        <Carousel v-bind="settings" :breakpoints="breakpoints">
                            <Slide v-for="slide in SLIDER_DATA" :key="slide.title">
                                <div class="carousel__item">
                                    <CameraIcon />
                                    {{ slide.title }}
                                </div>
                            </Slide>

                            <template #addons>
                                <Navigation />
                            </template>
                        </Carousel>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";

import CameraIcon from "./Icons/CameraIcon.vue";

import "vue3-carousel/dist/carousel.css";

import '../css/HeroBanner.scss'

export default defineComponent({
    name: "HeroBanner",
    components: {
        Carousel,
        Slide,
        Navigation,
    },
    data: () => ({
        SLIDER_DATA: [
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
            { title: "해외 마케팅" },
        ],

        TEXT_DATA: [
            {
                title: '평균 월 120만원',
                description: '임금을 해당 국가를 기준으로 계산합니다.'
            },
            {
                title: '최대 3회 인력교체',
                description: '막상 채용해보니 맞지 않아도 걱정하지 마세요.'
            },
            {
                title: '평균 3일, 최대 10일',
                description: '급하게 사람이 필요한 경우에도 빠른 채용이 가능합니다.'
            }
        ],
        // carousel settings
        settings: {
            itemsToShow: 3,
            snapAlign: "center",
        },
        // breakpoints are mobile first
        // any settings not specified will fallback to the carousel settings
        breakpoints: {
            // 700px and up
            700: {
                itemsToShow: 3.5,
                snapAlign: "center",
            },
            // 1024 and up
            1024: {
                itemsToShow: 5,
                snapAlign: "start",
            },
        },

    }),
});
</script>