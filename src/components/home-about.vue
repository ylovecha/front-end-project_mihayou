<script setup>
import home_about_decoration from '@/components/img/decoration.b195643.png'
import aside_slogan__line from '@/components/img/line.a3e37b6.png'
import { onMounted } from 'vue'

import Swiper from 'swiper'
import 'swiper/swiper-bundle.css'

onMounted(() => {
  new Swiper('.swiper-container', {
    direction: 'vertical',
    followFinger: false,
    speed: 800,
    mousewheel: true,
    pagination: {
      el: '.swiper-pagination'
    },
    on: {
      init(swiper) {
        const slide = swiper.slides.eq(0)
        slide.addClass('ani-slide')
      },
      transitionStart(swiper) {
        for (let i = 0; i < swiper.slides.length; i++) {
          const slide = swiper.slides.eq(i)
          slide.removeClass('ani-slide')
        }
      },
      transitionEnd(swiper) {
        const slide = swiper.slides.eq(swiper.activeIndex)
        slide.addClass('ani-slide')
      }
    }
  })
})
</script>

<template>
  <div class="home">
    <div class="home-about fp-page">
      <img :src="home_about_decoration" class="home-about-decoration" />
      <div data-v-5dd2d15e="" class="aside-slogan aside-slogan">
        <img data-v-5dd2d15e="" :src="aside_slogan__line" alt="miHoYo" class="aside-slogan__line" />
        <img
          data-v-5dd2d15e=""
          src="data:image/png;base64,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"
          alt="miHoYo"
          class="aside-slogan__text"
        />
      </div>
      <div class="fp-page__wrap">
        <!-----轮播的选择---->
        <div class="swiper-container swiper-container-initialized swiper-container-vertical">
          <div class="home-about-cates">
            <div class="home-about-cates-wrap home-about-cates-wrap--active">
              <div class="home-about-cate">
                <div
                  class="home-about-cate-wrap"
                  style="transform: translateY(-0.6rem); transition-duration: 0ms"
                >
                  <div class="span-wrapper"><span> 关于米哈游 </span></div>
                  <div class="span-wrapper">
                    <span class="tab-dark"> 关于米哈游 </span>
                  </div>
                  <div class="span-wrapper"><span> 关于米哈游 </span></div>
                </div>
              </div>
            </div>
            <div class="home-about-cates-wrap">
              <div class="home-about-cate">
                <div
                  class="home-about-cate-wrap"
                  style="transform: translateY(-0.6rem); transition-duration: 0ms"
                >
                  <div class="span-wrapper"><span> 发展历程 </span></div>
                  <div class="span-wrapper">
                    <span class="tab-dark"> 发展历程 </span>
                  </div>
                  <div class="span-wrapper"><span> 发展历程 </span></div>
                </div>
              </div>
            </div>
            <div class="home-about-cates-wrap">
              <div class="home-about-cate">
                <div
                  class="home-about-cate-wrap"
                  style="transform: translateY(-0.6rem); transition-duration: 0ms"
                >
                  <div class="span-wrapper"><span> 荣誉资质 </span></div>
                  <div class="span-wrapper">
                    <span class="tab-dark"> 荣誉资质 </span>
                  </div>
                  <div class="span-wrapper"><span> 荣誉资质 </span></div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="home-about-container">
          <div class="about-intro">
            <div class="about-intro__vision">
              <div class="about-intro__vision-title">
                我们的愿景
                <b> Our Vision</b>
              </div>
              <div class="about-intro__vision-slg">
                <div class="anim">
                  <p style="white-space: pre-wrap">2030年，打造出全球十亿人</p>
                  <p style="white-space: pre-wrap; text-align: right">愿意生活在其中的虚拟世界。</p>
                </div>
              </div>
            </div>
            <div class="about-intro__mihoyo">
              <div class="about-intro__mihoyo-title">
                关于米哈游
                <b> About miHoYo</b>
              </div>
              <div class="about-intro__mihoyo-desc">
                <div>
                  <p style="white-space: pre-wrap">
                    米哈游成立于2011年，致力于为用户提供美好的、超出预期的产品与内容。米哈游陆续推出了多款高品质人气产品，包括《崩坏学园2》、《崩坏3》、《未定事件簿》、《原神》、《崩坏：星穹铁道》，动态桌面软件《人工桌面》以及社区产品《米游社》，并围绕原创IP打造了动画、音乐及周边等多元产品。即将上线的《绝区零》等同样受到全球玩家广泛关注。
                  </p>
                  <p style="white-space: pre-wrap">
                    秉承着“<strong>技术宅拯救世界</strong>”的使命，米哈游始终致力于技术研发、探索前沿科技，在卡通渲染、人工智能、云游戏技术等领域积累了先进的技术能力。
                  </p>
                  <p style="white-space: pre-wrap">
                    米哈游总部位于中国上海，并在新加坡、美国、加拿大、日本、韩国等国家和地区进行全球化布局。目前，公司员工5,000人，来自世界知名游戏/互联网/科技公司。
                  </p>
                  <p style="white-space: pre-wrap; min-height: 1.5em"></p>
                  <p style="white-space: pre-wrap; min-height: 1.5em"></p>
                  <p style="white-space: pre-wrap">
                    <strong>米哈游的研发理念</strong>
                  </p>
                  <p style="white-space: pre-wrap">
                    Something New | Something Exciting | Something Out of Imagination
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/*header*/
.home {
  position: relative;

  width: 100%;

  height: 100%;
  font-family: 'Microsoft YaHei', 微软雅黑, 'MicrosoftJhengHei', PingFang, MingLiu, sans-serif;
}
.home-about {
  height: 100%;
  width: 100%;
  overflow: hidden;
}
/*swiper设置 */
.swiper-container {
  width: 800px;
  height: 200px;

  margin: 20px auto;
}

/* .swiper-slide {
  text-align: center;

  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
} */

/* .swiper-slide:nth-child(2) {
  background: #3183ff;
  color: #fff;
} */

/* .swiper-slide p {
  transform: translateX(-200px);
  opacity: 0;
  transition: all 0.4s;
}

.ani-slide p {
  transform: translateX(0);
  opacity: 1;
} */

/*左侧信息*/
.aside-slogan[data-v-5dd2d15e] {
  position: absolute;
  left: 1rem;
  bottom: 7.38rem;
}
.aside-slogan__line[data-v-5dd2d15e] {
  position: absolute;
  top: -13rem;
  left: -0.2rem;
  width: 10rem;
  height: 20.28rem;
  background: url(./components/img/line.a3e37b6.png) no-repeat center center/100% 100%;
}
.aside-slogan__text[data-v-5dd2d15e] {
  position: relative;
  top: 6rem;
  left: 2.2rem;
  z-index: 1;
  width: 0.4rem;
}
/*右侧 aboutus*/
.home-about-decoration {
  position: absolute;
  top: 0.9rem;
  right: 1rem;
  width: 10rem;
}
.home-about-decoration {
  -webkit-transition-delay: 2000ms;
  -o-transition-delay: 2000ms;
  transition-delay: 2000ms;
  -webkit-transition:
    opacity 1500ms,
    -webkit-transform 1500ms;
  transition:
    opacity 1500ms,
    -webkit-transform 1500ms;
  -o-transition:
    opacity 1500ms,
    transform 1500ms;
  transition:
    opacity 1500ms,
    transform 1500ms;
  transition:
    opacity 1500ms,
    transform 1500ms,
    -webkit-transform 1500ms;
}

/* home-about-cates */
.home-about-cates {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: end;
  justify-content: flex-end;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin-bottom: 10rem;
  margin-right: 2rem;
  top: 1px;
}
.home-about-cates {
  -webkit-transition: -webkit-transform 800ms;
  transition: -webkit-transform 800ms;
  -o-transition: transform 800ms;
  transition: transform 800ms;
  transition:
    transform 800ms,
    -webkit-transform 800ms;
  -webkit-transition-delay: 200ms;
  -o-transition-delay: 200ms;
  transition-delay: 200ms;
}
.home-about-cates-wrap {
  /**应用于子元素，用于包装关于米哈游的内容 */
  position: relative;

  /* overflow: hidden; */ /**超出内容部分隐藏。 */
  margin-right: -1px;
  cursor: pointer; /*可以点击 */
}
.home-about-cate {
  height: 40px;
  width: 80px;
  overflow: hidden;
}
.home-about-cate-wrap {
  font-size: 0;
  color: #676b73;
  white-space: nowrap; /**防止文本换行 */
  position: relative;
  height: 40px;
  width: 80px;
  -webkit-transform: translateY(-0.6rem); /**设置垂直方向上的位移，可能是为了添加动画效果 */
  -ms-transform: translateY(-0.6rem);
  transform: translateY(-0.6rem);
}

.home-about-cates-wrap::before,
.home-about-cates-wrap::after {
  /**用于在 .home-about-cates-wrap 元素的前后添加一个竖线 */
  content: '';
  position: absolute;
  top: 50%;
  width: 3px;
  height: 40px;
  background: #707173;
  -webkit-transform: translateY(-50%);
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
.home-about-cates-wrap::before {
  left: 0;
}
.home-about-cates-wrap::after {
  right: 0;
}

.home-about-cates-wrap:hover::before,
.home-about-cates-wrap:hover::after,
.home-about-cates-wrap--active::before,
.home-about-cates-wrap--active::after {
  background-color: #3778e5;
}
.home-about-cates-wrap:hover + .home-about-cates-wrap::before,
.home-about-cates-wrap--active + .home-about-cates-wrap::before {
  background-color: #3778e5;
}
.home-about-cates-wrap--active {
  /**被点击选中 */
  color: #fff;
}
.home-about-cates-wrap--active .home-about-cate-wrap {
  -webkit-transform: translateY(-0.6rem);
  -ms-transform: translateY(-0.6rem);
  transform: translateY(-0.6rem);
}
.home-about-cates-wrap--active span {
  color: #fff;
  background-color: #3778e5;
}

.home-about-cate .span-wrapper {
  height: 50px;
  width: 80px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  overflow: hidden;
}
.home-about-cate span {
  display: block;
  font-size: 0.7rem;
  height: 50px;
  line-height: 3.5rem;
  position: relative;
  padding: 0 0.7rem;
}
.home-about-cate .tab-dark {
  color: #fff;
  background: #3778e5;
}
.about-fade-enter-active,
.about-fade-leave-active {
  -webkit-transition: opacity 700ms;
  -o-transition: opacity 700ms;
  transition: opacity 700ms;
}
.about-fade-enter,
.about-fade-leave-to {
  opacity: 0;
}

/*内容*/
.home-about-container {
  position: relative;
  width: 1000px;
  height: 400px;
  bottom: 160px;
  left: 100px;
}
.home-about-container > div {
  position: absolute;
  left: 50%;
  top: 0;
  -webkit-transform: translateX(-50%);
  -ms-transform: translateX(-50%);
  transform: translateX(-50%);
}
.home-about-container {
  -webkit-transition: -webkit-transform 800ms;
  transition: -webkit-transform 800ms;
  -o-transition: transform 800ms;
  transition: transform 800ms;
  transition:
    transform 800ms,
    -webkit-transform 800ms;
  -webkit-transition-delay: 200ms;
  -o-transition-delay: 200ms;
  transition-delay: 200ms;
}

.about-intro {
  width: 98%;
  height: 100%;
  padding-left: 19rem;
}
.about-intro img {
  width: 100%;
}
.about-intro__vision {
  max-height: 400px;
}
.about-intro__vision-title,
.about-intro__mihoyo-title {
  position: relative;
  margin-bottom: 1rem;
  font-size: 1.3rem;
  font-weight: bold;
  color: #242933;
}
.about-intro__vision-title b,
.about-intro__mihoyo-title b {
  position: absolute;
  left: 6rem;
  bottom: -0.6rem;
  font-size: 0.5rem;
  font-weight: normal;
  color: #ccc;
  letter-spacing: 0.1em;
  font-family: HarmonyOS, Arial, Helvetica, sans-serif;
  text-transform: uppercase;
}
/**彩字设置 */
.about-intro__vision-slg {
  position: relative;
  display: inline-block;

  width: calc(100% - 15.76rem);
  padding-left: 3.2rem;
  width: 730px;
  margin-bottom: 1.4rem;
  margin-left: 3.64rem;
  font-size: 2.3rem;
  line-height: 2.3rem;
  letter-spacing: 0.1em;
  font-weight: lighter;
  color: #4ea1d9;
}
.about-intro__vision-slg.pureColor {
  background: none;
  pointer-events: none;
}
.about-intro__vision-slg.pureColor em {
  background: none;
  -webkit-background-clip: none;
}
.about-intro__vision-slg strong {
  color: #74d5ee;
  font-weight: inherit;
}
.about-intro__vision-slg em {
  color: #418ae0;
  font-style: normal;
  background-image: -o-linear-gradient(225deg, #dc8bc3 0, #418ae0 100%);
  background-image: linear-gradient(-135deg, #dc8bc3 0, #418ae0 100%);
  -webkit-text-fill-color: rgba(0, 0, 0, 0);
  -webkit-background-clip: text;
}
.about-intro__vision-slg u {
  color: #dc8bc3;
  text-decoration: none;
}
.about-intro__vision-slg::before,
.about-intro__vision-slg::after {
  content: '';
  position: absolute;
  width: 0.38rem;
  height: 1.25rem;
  background-repeat: 0;
  background-size: cover;
  background-position: center center;
}
.about-intro__vision-slg::before {
  left: 0;
  top: 0;
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAZCAYAAAAMhW+1AAAAAXNSR0IArs4c6QAAACZJREFUOE9j9Ft48z8DHsBIXQWb4tUZ0W1DsWJUASR4RsNhcIcDADoPYG82O/IpAAAAAElFTkSuQmCC);
}
.about-intro__vision-slg::after {
  right: 0;
  bottom: 0;
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAZCAYAAAAMhW+1AAAAAXNSR0IArs4c6QAAAChJREFUOE9jZMACrsx98h8mzDiqABwCo+EASQhDIxyQUzC2BMxIsQIAEOdTTmAeOPYAAAAASUVORK5CYII=);
}
.about-intro__vision-slg .anim {
  background-image: -o-linear-gradient(
    225deg,
    #418ae0,
    #56a0d8,
    #dc8bc3,
    #56a0d8,
    #418ae0,
    #56a0d8,
    #dc8bc3,
    #56a0d8,
    #418ae0
  );
  background-image: linear-gradient(
    -135deg,
    #418ae0,
    #56a0d8,
    #dc8bc3,
    #56a0d8,
    #418ae0,
    #56a0d8,
    #dc8bc3,
    #56a0d8,
    #418ae0
  );
  background-image: -ms-linear-gradient(
    -135deg,
    #418ae0,
    #56a0d8,
    #dc8bc3,
    #56a0d8,
    #418ae0,
    #56a0d8,
    #dc8bc3,
    #56a0d8,
    #418ae0
  );
  -webkit-text-fill-color: rgba(0, 0, 0, 0);
  -webkit-background-clip: text;
  background-size: 200% 100%;
  -webkit-animation: masked-animation 3s infinite linear;
  animation: masked-animation 3s infinite linear;
}
@-webkit-keyframes masked-animation {
  0% {
    background-position: 0 -100%;
  }
  100% {
    background-position: -100% 0;
  }
}
@keyframes masked-animation {
  0% {
    background-position: 0 -100%;
  }
  100% {
    background-position: -100% 0;
  }
}
.about-intro__mihoyo-desc {
  text-align: left;
  margin-bottom: 0.7rem;
  font-size: 0.8rem;
  color: #3d424d;
  line-height: 1.34rem;
  height: 2rem;
}
.about-intro__mihoyo-desc p {
  margin-bottom: 0.1rem;
}
.about-intro__mihoyo-desc strong {
  color: #3778e5;
  font-weight: bold;
}
</style>
