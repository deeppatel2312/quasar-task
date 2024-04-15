<template>
    <div class="hero-banner-wrapper">
        <div class="container">
            <div class="row flex-center">
                <div class="col-lg-6 col-sm-6">
                    <div class="animated fadeIn delay-3s">
                        <img src="../assets/HeroBannerMainBadge.svg" />
                    </div>
                    <div class="animated fadeInUp delay-1s">
                        <h1>최고의 실력을 가진 외국인 인재를 찾고 계신가요?</h1>
                    </div>

                    <div class="animated fadeInUp delay-1s">
                        <h4>법률 및 인사관리 부담없이 1주일 이내에 원격으로 채용해보세요.</h4>
                        <h6>개발자가 필요하신가요?</h6>
                    </div>

                    <div class="row">
                        <div class="col-lg-4" v-for="text in TEXT_DATA" :key="text.title">
                            <div class="text-wrap">
                                <div class="animated fadeInUp delay-1s">
                                    <h6>{{ text.title }}</h6>
                                    <p>{{ text.description }}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="col-lg-6 col-sm-6">
                    <div class="firstSlider">
                        <div class="animated fadeIn delay-3s">
                            <img src="../assets/HeroBannerSecondBadge.svg" class="badgeImage" />
                        </div>
                        <div class="animated fadeInUp delay-1s">
                            <Carousel :itemsToScroll="1" :itemsToShow="2.5" :wrap-around="true">
                                <Slide v-for="slide in 10" :key="slide">
                                    <div class="carousel__item">
                                        <img src="../assets/SliderImage.png" />
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

        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <div class="mobileOnly">
                        <div class="flex" v-for="mobile in MOBILE_DATA" :key="mobile.title1">
                            <div>
                                <component :is="mobile.icon" /> {{ mobile.title1 }}
                            </div>
                            <div>
                                <component :is="mobile.icon" /> {{ mobile.title2 }}
                            </div>
                        </div>
                        <a href="#" class="mobileOnly__btn">개발자가 필요하신가요?</a>
                    </div>
                </div>
            </div>
        </div>

        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <div class="animated fadeInUp delay-1s">
                        <div class="secondSlider">
                            <Carousel v-bind="settings" :autoplay="5000" :wrap-around="false"
                                :breakpoints="breakpoints">
                                <Slide v-for="slide in SLIDER_DATA" :key="slide.title">
                                    <div class="carousel__item">
                                        <CameraIcon /> {{ slide.title }}
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

    </div>
</template>

<script setup>

import CameraIcon from "./Icons/CameraIcon.vue";
import CheckIcon from "./Icons/CheckIcon.vue";

defineOptions({
    name: 'HeroBanner'
})

</script>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";
import '../css/HeroBanner.scss'

export default defineComponent({
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

        MOBILE_DATA: [
            {
                title1: '한국어 능력',
                title2: '업무 수행 능력',
                icon: CheckIcon
            },
            {
                title1: '겸업 여부',
                title2: '평판 조회',
                icon: CheckIcon
            },
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
        settings: {
            itemsToShow: 3,
            snapAlign: "center",
        },
        breakpoints: {
            320: {
                itemsToShow: 1,
                snapAlign: "center",
            },
            700: {
                itemsToShow: 1,
                snapAlign: "center",
            },
            1024: {
                itemsToShow: 5,
                snapAlign: "center",
            },
        },

    }),
});
</script>