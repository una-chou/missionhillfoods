<template>
  <div class="scroll-container">
    <div class="manufacture-content-box common-box">
      <Header />
      <div class="manufacture-content-box-center">
        <div class="detail-page-title">
          <div class="detail-page-title-left detail-page-title-left-pc">
            <div>Our Manufacturing </div>
            <div class="detail-page-second">Facilities</div>
          </div>
          <div class="detail-page-title-left detail-page-title-left-m">
            <div>Our Manufacturing Facilities</div>
          </div>
          <div class="detail-page-title-right">
            <img src="@/assets/images/micon4.png" style="position: relative;top: -25px;">
            <img src="@/assets/images/micon5.png" style="width:94px" alt="">
            <img src="@/assets/images/company-right1.png" alt="">
            <img src="@/assets/images/company-right2.png" alt="">
          </div>
        </div>
        <div class="manufacture-video">
          <el-carousel :autoplay="true" arrow="never">
            <el-carousel-item>
              <div class="top-swiper">
                <img src="@/assets/images/manufacture1.png" alt="">
              </div>
            </el-carousel-item>
            <el-carousel-item>
              <div class="top-swiper">
                <img src="@/assets/images/manufacture2.jpg" alt="">
              </div>
            </el-carousel-item>
            <el-carousel-item>
              <div class="top-swiper">
                <img src="@/assets/images/manufacture3.jpg" alt="">
              </div>
            </el-carousel-item>
          </el-carousel>
        </div>

        <div class="manufacture-introduce">
          <div>Our manufacturing facilities include two sites in: Richmond, BC, Canada and Chino, California, USA.</div>
          <div>We supply various dosage forms including softgel, capsule, tablet, powder (sachet and jar), pill, granule, oral liquid, drops, functional beverage (bottle and portable pouch), with over 200 kinds of formulas, and a daily production capacity of 900,000 bottles (boxes. sachets).</div>
        </div>


        <div class="MANUFACTURING MANUFACTURING-pc">

          <div class="manufacture-swiper">
            <div class="manufacture-swiper-container">
              <swiper class="swiper" :options="swiperOption">
                <swiper-slide v-for="(item,index) in LabLists" :key="index">
                  <div class="manufacture-swiper-content">
                    <div class="manufacture-image" :class="`manufacture-image${index+1}`">
                      <img :src="item.picture" alt="">
                    </div>
                    <div class="manufacture-name">{{ item.name }}</div>
                  </div>
                </swiper-slide>
              </swiper>
              <div class="swiper-pagination" slot="pagination"></div>
              <div class="swiper-button-prev" slot="button-prev">
                <img src="./../../assets/images/swiper-arrow1.png" alt="">
              </div>
              <div class="swiper-button-next" slot="button-next">
                <img src="./../../assets/images/swiper-arrow2.png" alt="">
              </div>
            </div>
          </div>
        </div>

        <div class="MANUFACTURING MANUFACTURING-m">

          <div class="manufacture-swiper">
            <div class="manufacture-swiper-container">
              <swiper class="swiper" :options="swiperOptionMobile">
                <swiper-slide v-for="(item,index) in LabLists" :key="index">
                  <div class="manufacture-swiper-content">
                    <div class="manufacture-image" style="height:100%;width:auto" :class="`manufacture-image${index+1}`">
                      <img :src="item.picture" alt="">
                    </div>
                    <div class="manufacture-name">{{ item.name }}</div>
                  </div>
                </swiper-slide>
              </swiper>
              <div class="swiper-pagination" slot="pagination"></div>
              <div class="swiper-button-prev" slot="button-prev">
                <img src="./../../assets/images/swiper-arrow1.png" alt="">
              </div>
              <div class="swiper-button-next" slot="button-next">
                <img src="./../../assets/images/swiper-arrow2.png" alt="">
              </div>
            </div>
          </div>
          </div>

        <div class="common-titles">OUR PRODUCTION CAPACITY</div>

        <div class="CAPACITY-lists">
          <div>
            <div class="CAPACITY-items" v-for="(item,index) in CapacityList" :key="index">
              <img :src="item.picture" alt="">
              <p>{{item.name}}</p>
              <span>{{ item.desc }}</span>
            </div>
          </div>
        </div>

        <div class="provide-fda">
          <div class="provide-fda-text">We can provide full service from raw materials to finished products with various packaging forms including bottling, box packaging and blistering.Our manufacturing procedure strictly follows the regulations and standards of US FDA and cGMP standards.</div>
          <div class="provide-fda-image">
            <img class="provide-fda-image-left" src="@/assets/images/micon4.png" alt="">
            <img src="@/assets/images/micon5.png" alt="">
          </div>
        </div>

        <div class="common-titles" style="margin:30px 0 20px">OUR QUALITY MANAGEMENT</div>

        <div class="quality-lists">
          <div class="quality-items" :class="`quality-items${index+1}`" v-for="(item,index) in QualityLists" :key="index">
            <img :src="item.picture" alt="">
            <div>{{ item.desc }}</div>
          </div>
        </div>
      </div>

      

      <div class="manufacture-content-box-center">
        <NutritionLab />
      </div>

    </div>
    <Footer />
  </div>
</template>
<script>
import Footer from '@/components/Footer.vue'
import Header from '@/components/Header.vue'
import NutritionLab from '@/components/NutritionLab.vue'
import {LabLists} from '@/products.js'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'
import {QualityLists, CapacityList} from './data.js'

export default {
  components: { Header, Footer, Swiper, SwiperSlide, NutritionLab },
  props: {},
  data() {
    return {
      LabLists,
      QualityLists,
      CapacityList, 
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 20,
        // pagination: {
        //   el: '.swiper-pagination',
        //   clickable: true
        // },
        pagination: false,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      },
      swiperOptionMobile: {
        slidesPerView: 1,
        spaceBetween: 20,
        // pagination: {
        //   el: '.swiper-pagination',
        //   clickable: true
        // },
        pagination: false,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      }
    }
  },
  created() {
  },
  mounted() {
  },
  methods: {
    
  }
}
</script>
<style lang='scss'>
.manufacture-video {
  width: 100%;
  height: 800px;
  .top-swiper {
    width: 100%;
    height: 100%;
    position: relative;
    cursor: pointer;
    &>img {
      height: 100%;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    .top-swiper-text {
      color: #fff;
      position: absolute;
      bottom: 110px;
      font-size: 60px;
      width: 100%;
      text-align: center;
      font-weight: bold;
    }
  }
  .el-carousel, .el-carousel__container {
    height: 100%;
    .el-carousel__indicator--horizontal {
      padding: 12px 8px 40px;
    }
    .el-carousel__indicators {

      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: row;
    }
    .el-carousel__indicator {
      // background-color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: row;
      .el-carousel__button {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        opacity: 1;

      }
    }
    .el-carousel__indicator.is-active button {
      width: 14px;
      height: 14px;
      background-color: $green;
    }
  }
}
.manufacture-content-box {
  width: 100%;
  .detail-page-title-right {
    img {
      height: auto;
      margin-left: 25px;
    }
  }
  .manufacture-content-box-center {

    padding: 0 $padding;
    .detail-page-title-left-pc {
      display: block;
    }
    .detail-page-title-left-m {
      display: none;
    }
  }
  .manufacture-introduce {
    font-size: 24px;
    line-height: 1.6;
    color: #000;
    padding: 40px 0 60px;
  }
  .CAPACITY-lists {
    width: 100%;
    margin-bottom: 60px;
    &>div {
      width: 100%;
      display: flex;
      align-items: flex-start;
      justify-content: center;
      flex-wrap: wrap;
    }
    .CAPACITY-items {
      width: 33.33%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      color: #000;
      font-size: 28px;
      margin-bottom: 50px;
      padding: 0 20px;
      &>img {
        width: 80px;
        margin-bottom: 20px;
      }
      &>p {

      }
      &>span {

      }

    }
  }
  .provide-fda {
    border: 1px solid #000;
    border-radius: 35px;
    padding: 40px 50px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .provide-fda-text {
      padding-right: 20px;
      color: #000;
      font-size: 24px;
      line-height: 1.5;
    }
    .provide-fda-image {
      display: flex;
      flex-shrink: 0;
      align-items: center;
      img {
        width: 100px;
        height: 100px;
        height: max-content;
        margin-left: 30px;
        flex-shrink: 0;
      }
      .provide-fda-image-left {
        height: 40px;
      }
    }
  }
  .quality-lists {
    padding: 0 40px;
    .quality-items {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 0 40px;
      &>img {
        // width: 110px;
        height: 80px;
        padding: 10px 0;
      }
      &>div {
        font-size: 24px;
        line-height: 1.5;
        padding: 40px 0;
        text-align: center;
      }
    }
    .quality-items1 {
      position: relative;
      &::before {
        content: '';
        display: block;
        background: url('./../../assets/images/arrow.png') no-repeat top left;
        width: 16px;
        height: 34px;
        background-size: 100% 100%;
        position: absolute;
        bottom: -66px;
        left: calc( 42% - 15px );
      }
      &::after {
        content: '';
        display: block;
        height: calc( 100% + 20px );
        width: 42%;
        background-size: 100% 100%;
        position: absolute;
        top: 30px;
        left: 0;
        border: 1px solid $green;
        border-right: unset;
        border-radius: 20px 0 0 20px;
      }
    }
    .quality-items2 {
      position: relative;
      &::before {
        content: '';
        display: block;
        background: url('./../../assets/images/arrow.png') no-repeat top left;
        transform: rotate(180deg);
        width: 16px;
        height: 34px;
        background-size: 100% 100%;
        position: absolute;
        bottom: -61.6px;
        right: calc( 42% - 15px );
      }
      &::after {
        content: '';
        display: block;
        // background: url('./../../assets/images/border-arrow.png') no-repeat top left;
        height: calc( 100% - 4px);
        width: 42%;
        background-size: 100% 100%;
        position: absolute;
        top: 49px;
        right: 0;
        border: 1px solid $green;
        border-left: unset;
        border-radius: 0 20px 20px 0;
      }
    }
  }
}
.MANUFACTURING {
  padding-top: 10px;
  .manufacture-swiper {
    // padding: 0 70px;
    // height: 400px;
    overflow: hidden;
    // margin-top: 50px;
    // position: relative;
    .manufacture-swiper-container {
      width: 100%;
      height: 380px;
      position: relative; /* 确保相对定位的正确性 */
      padding: 0 70px;

      .swiper {
        height: 100%;
        width: 100%;
        .swiper-slide {
          // background-color: red;
        }
      }
      .swiper-pagination {
        bottom: -50px;
        position: absolute;
        text-align: center;
        transition: 300ms opacity;
        transform: translate3d(0, 0, 0);
        z-index: 10;
        left: 0;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        .swiper-pagination-bullet {
          margin: 0 8px;
        }
      }
      .swiper-button-prev,
      .swiper-button-next {
        position: absolute;
        // top: 50%;
        // transform: translateY(-50%);
        top: 160px;
        width: 30px;
        height: 30px;
        // color: $greenText;
        // border-radius: 50%;
        cursor: pointer;
        z-index: 10;
        // border: 2px solid $greenText;
        // font-size: 26px;
        // font-weight: bold;
        img {
          width: 100%;
          height: 100%;
        }
        &::after {
          content: '';
        }
        &:hover {
          // color: #fff;
          // background-color: $greenText;
          opacity: .9;          
        }
      }
      .swiper-button-prev {
        left: 0px;
      }
      .swiper-button-next {
        right: 0px;
      }
      .swiper-pagination-bullet {
        background-color: #AAABAB;
        opacity: 1;
        width: 10px;
        height: 10px;

      }
      .swiper-pagination-bullet-active {
        background-color: $green;
        width: 14px;
        height: 14px;
      }
    }
    .manufacture-swiper-content {
      .manufacture-image {
        height: 300px;
        position: relative;
        overflow: hidden;
        border-radius: 12px;
        &>img {
          // width: 100%;
          height:100%;
          max-width: 100%;
          max-height: 100%;
          transition: all 0.6s ease;
          transform: translate(-50%, -50%);
          position: absolute;
          top: 50%;
          left: 50%;

        }
      }
      .manufacture-image4 {
        &>img {
          width:100%;
          height: auto;
        }
      }
      .manufacture-image5 {
        &>img {
          height:100%;
          width: auto;
        }
      }
      .manufacture-name {
        font-size: 23px;
        color: #000;
        padding-top: 28px;
        text-align: center;
      }
    }
  }
}
.MANUFACTURING-pc {
  display: block;
}
.MANUFACTURING-m {
  display: none;
}


@media only screen and (max-width: 1200px) {
.manufacture-content-box {
  .CAPACITY-lists {
    .CAPACITY-items {
      font-size: 26px;
    }
  }
}
}

@media only screen and (max-width: 1100px) {
.manufacture-content-box {
  .CAPACITY-lists {
    .CAPACITY-items {
      font-size: 19px;
    }
  }
  .manufacture-introduce {
    padding-bottom: 30px
  }
  .MANUFACTURING {
    padding-top: 10px;
    .manufacture-swiper {
      // padding: 0 70px;
      // height: 400px;
      overflow: hidden;
      // margin-top: 50px;
      // position: relative;
      .manufacture-swiper-container {
        width: 100%;
        height: 300px;
        position: relative; /* 确保相对定位的正确性 */
        padding: 0 70px;

        .swiper {
          height: 100%;
          width: 100%;
          .swiper-slide {
            // background-color: red;
          }
        }
        .swiper-pagination {
          bottom: -50px;
          position: absolute;
          text-align: center;
          transition: 300ms opacity;
          transform: translate3d(0, 0, 0);
          z-index: 10;
          left: 0;
          width: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          .swiper-pagination-bullet {
            margin: 0 8px;
          }
        }
        .swiper-button-prev,
        .swiper-button-next {
          position: absolute;
          // top: 50%;
          // transform: translateY(-50%);
          top: 160px;
          width: 30px;
          height: 30px;
          // color: $greenText;
          // border-radius: 50%;
          cursor: pointer;
          z-index: 10;
          // border: 2px solid $greenText;
          // font-size: 26px;
          // font-weight: bold;
          img {
            width: 100%;
            height: 100%;
          }
          &::after {
            content: '';
          }
          &:hover {
            // color: #fff;
            // background-color: $greenText;
            opacity: .9;          
          }
        }
        .swiper-button-prev {
          left: 0px;
        }
        .swiper-button-next {
          right: 0px;
        }
        .swiper-pagination-bullet {
          background-color: #AAABAB;
          opacity: 1;
          width: 10px;
          height: 10px;

        }
        .swiper-pagination-bullet-active {
          background-color: $green;
          width: 14px;
          height: 14px;
        }
      }
      .manufacture-swiper-content {
        .manufacture-image {
          height: 260px;
          position: relative;
          overflow: hidden;
          border-radius: 12px;
          &>img {
            width: 100%;
            // height:100%;
            transition: all 0.6s ease;
            transform: translate(-50%, -50%);
            position: absolute;
            top: 50%;
            left: 50%;

          }
        }
        .manufacture-image5 {
          &>img {
            height:100%;
            width: auto;
          }
        }
        .manufacture-name {
          font-size: 18px;
          color: #000;
          padding-top: 18px;
          text-align: center;
        }
      }
    }
  }
}
}

@media only screen and (max-width: 900px) {
.manufacture-video {
  width: 100%;
  height: 400px;
  .el-carousel, .el-carousel__container {
    height: 100%;
    .el-carousel__indicator--horizontal {
      padding: 12px 8px 10px;
    }
    .el-carousel__indicator {
      .el-carousel__button {
        width: 8px;
        height: 8px;
      }
    }
    .el-carousel__indicator.is-active button {
      width: 12px;
      height: 12px;
    }
  }
}
.manufacture-content-box {
  width: 100%;
  .detail-page-title-right {
    img {
      height: auto;
      margin-left: 25px;
    }
  }
  .manufacture-content-box-center {
    padding: 0 20px;
    .detail-page-title-left-pc {
      display: none;
    }
    .detail-page-title-left-m {
      display: block;
    }
    .detail-page-title {
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
      padding: 20px 0;
    }
    .detail-page-title-left {
      font-size: 22px;
      line-height: 1.8;
    }
    .detail-page-title-right {
      margin-top: 10px;
      &>img {
        width: 50px !important;
        height: auto;
        margin-left: 0;
        margin-right: 10px;
        &:first-child {
          top: -15px !important;
        }
      }
    }
  }
  .manufacture-introduce {
    font-size: 16px;
    line-height: 1.5;
    padding: 20px 0;
  }
  .CAPACITY-lists {
    width: 100%;
    margin-bottom: 10px;
    .CAPACITY-items {
      width: 50%;
      font-size: 14px;
      margin-bottom: 20px;
      padding: 0 0px;
      &>img {
        width: 50px;
        margin-bottom: 10px;
      }

    }
  }
  .provide-fda {
    border-radius: 12px;
    padding: 20px;
    flex-direction: column;
    margin-bottom: 20px;
    .provide-fda-text {
      padding-right: 0px;
      font-size: 16px;
      line-height: 1.5;
      text-align: center;
    }
    .provide-fda-image {
      align-items: center;
      margin-top: 20px;
      img {
        width: 60px;
        height: 60px;
        margin-left: 0px;
        margin-right: 10px;
      }
      .provide-fda-image-left {
        height: 24px;
        margin-right: 20px;
      }
    }
  }
  .common-titles {
    padding: 20px 0;
    margin: 0 !important;
    font-size: 22px;
  }
  .quality-lists {
    padding: 0 20px;
    .quality-items {
      padding: 0 20px;
      &>img {
        height: 50px;
        padding: 10px 0;
      }
      &>div {
        font-size: 14px;
        line-height: 1.5;
        padding: 20px 0;
      }
    }
    .quality-items1 {
      &::before {
        bottom: -46px;
      }
      &::after {
        height: calc( 100% + 0px );
      }
    }
    .quality-items2 {
      &::before {
        bottom: -41.6px;
      }
      &::after {
        top: 29px;
      }
    }
  }
}
.MANUFACTURING-pc {
  display: none;
}
.MANUFACTURING-m {
  display: block;

  .manufacture-swiper {
    overflow: hidden;
    .manufacture-swiper-container {
      width: 100%;
      height: 350px;
      position: relative; /* 确保相对定位的正确性 */
      padding: 0 30px;

      .swiper {
        height: 100%;
        width: 100%;
        .swiper-slide {
          // background-color: red;
        }
      }
      .swiper-pagination {
        bottom: -50px;
        position: absolute;
        text-align: center;
        transition: 300ms opacity;
        transform: translate3d(0, 0, 0);
        z-index: 10;
        left: 0;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        .swiper-pagination-bullet {
          margin: 0 8px;
        }
      }
      .swiper-button-prev,
      .swiper-button-next {
        top: 160px;
        width: 25px;
        height: 25px;
        img {
          width: 100%;
          height: 100%;
        }
        &::after {
          content: '';
        }
        &:hover {
          opacity: 1;          
        }
      }
      .swiper-button-prev {
        left: 0px;
      }
      .swiper-button-next {
        right: 0px;
      }
      .swiper-pagination-bullet {
        background-color: #AAABAB;
        opacity: 1;
        width: 10px;
        height: 10px;
      }
      .swiper-pagination-bullet-active {
        background-color: $green;
        width: 14px;
        height: 14px;
      }
    }
    .manufacture-swiper-content {
      .manufacture-image {
        height: 300px;
        position: relative;
        overflow: hidden;
        border-radius: 12px;
        &>img {
          width: 100%;
          transition: all 0.6s ease;
          transform: translate(-50%, -50%);
          position: absolute;
          top: 50%;
          left: 50%;

        }
      }
      .manufacture-image5 {
        &>img {
          height:100%;
          width: auto;
        }
      }
      .manufacture-name {
        font-size: 16px;
        color: #000;
        padding-top: 18px;
        text-align: center;
      }
    }
  }
}
}
</style>