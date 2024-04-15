<template>
    <footer>
        <div class="footerComponent">
            <div class="container">
                <div class="row">
                    <div class="col-lg-4 col-sm-4">
                        <div class="footerComponent__LogoWrapper">
                            <img src="../assets/LogoFooter.svg" alt="" />
                            <span>우리는 국가의 장벽을 넘어 최고의 인재를 매칭해드립니다.</span>
                            <ul>
                                <li>
                                    <a href="#">010-0000-0000</a>
                                </li>
                                <li>
                                    <a href="#">aaaaa@naver.com</a>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <div class="col-lg-8 col-sm-8">
                        <div class="row">
                            <div class="col-lg-3 col-sm-6" v-for="({ title, icon }) in FOOTER_DATA" :key="title">
                                <div class="footerComponent__LinksWrapper">
                                    <component :is="icon" />
                                    <span> {{ title }} </span>
                                    <a href="#">바로가기
                                        <ButtonArrow />
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="row">
                    <div class="col-lg-4 col-sm-4">
                        <div class="footerComponent__LeftLinks">
                            <div class="flex">
                                <div>
                                    <span>상호명</span>
                                    <span>하이퍼하이어</span>
                                    <span>Hyperhire India Private Limited</span>
                                </div>
                                <div>
                                    <span>대표 CEO</span>
                                    <span>김주현</span>
                                    <span>Juhyun Kim</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-8 col-sm-8">
                        <div class="row">
                            <div class="col-lg-3 col-sm-5">
                                <div class="footerComponent__RightLinks">
                                    <p>사업자등록번호 CIN</p>
                                    <span>427-86-01187</span>
                                    <span>U74110DL2016PTC290812 </span>
                                </div>
                            </div>
                            <div class="col-lg-9 col-sm-7">
                                <div class="footerComponent__RightLinks">
                                    <p>주소 ADDRESS</p>
                                    <span>서울특별시 강남대로 479, 지하 1층 238호 </span>
                                    <span>D-138, Street number 11, Jagjeet Nagar, North East Delhi, New Delhi,
                                        110053 India </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>

import { defineComponent } from 'vue';
import FooterLinksIcon from './Icons/FooterLinksIcon.vue';
import FooterUserIcon from './Icons/FooterUserIcon.vue';
import ButtonArrow from './Icons/ButtonArrow.vue';
import FooterIconKOR from './Icons/FooterIconKOR.vue';
import FooterIconSettings from './Icons/FooterIconSettings.vue';
import '../css/Footer.scss'

defineOptions({
    name: 'FooterComponent'
})

</script>

<script>
export default defineComponent({
    data: () => ({
        FOOTER_DATA: [
            {
                title: '해외 개발자 원격 채용',
                icon: FooterLinksIcon
            },
            {
                title: '해외 개발자 원격 채용',
                icon: FooterUserIcon
            },
            {
                title: '해외 개발자 원격 채용',
                icon: FooterIconKOR
            },
            {
                title: '해외 개발자 원격 채용',
                icon: FooterIconSettings
            }
        ]
    })
})
</script>