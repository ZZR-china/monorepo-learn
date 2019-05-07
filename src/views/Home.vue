<template>
  <div class="home">
    <!-- swiper -->
    <swiper :options="swiperOption" class="container">
      <swiper-slide class="part1" data-hash="slide1">
        <header class="header">
          <el-row :gutter="20" type="flex" class="row-bg" justify="space-between">
            <el-col :span="6" style="text-align:left;padding-left:0;margin-left: -2px;" :pull="0">
              <img src="../assets/images/pc_ico_logo.png" style="width: 90px;height: auto;" alt="logo">
            </el-col>
            <el-col :span="14" :push="0">
              <el-row :gutter="0" type="flex" justify="center" class="menu">
                <el-col :span="4" v-for="item in header" :key="item">
                  <span>{{item}}</span>
                </el-col>
              </el-row>
            </el-col>
          </el-row>
        </header>
        <swiper :options="part1swiperOption" class="part1-swiper">
          <swiper-slide>
            <img src="../assets/images/banner/ban_1.png" alt="banner1">
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/banner/ban_2.png" alt="banner2">
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/banner/ban_3.png" alt="banner3">
          </swiper-slide>
          <div class="swiper-pagination swiper-pagination-part1" slot="pagination"></div>
        </swiper>
        <div class="part1-footer">
          <el-row :gutter="0" type="flex" justify="center">
            <el-col :span="6" v-for="item in part1Footer" :key="item">
              <img :src="item.img" :alt="item.text">
              <div class="tips">{{item.text}}</div>
              <div class="hover-tips">
                <div class="title">
                  <span>{{item.hovertitle}}</span>
                </div>
                <div class="text" v-for="iitem in item.hovertext" :key="iitem">{{iitem}}</div>
              </div>
            </el-col>
          </el-row>
        </div>
      </swiper-slide>
      <swiper-slide class="part2" data-hash="slide2">
        <HomeHeader />
        <div class="part2-main">
          <el-row type="flex" justify="center" class="row-bg">
            <el-col :span="6"  
            v-for="item in part2List" 
            :key="item.text">
              <div class="elem" >
                <div class="elem-main" :style="{backgroundImage:'url(' + item.bgImg + ')'}">
                  <div class="elem-main-circle">
                    {{item.text}}
                  </div>
                  <div class="elem-main-block">
                    <div class="elem-main-block__circle part2__circle">
                      <img :src="item.topImg" :alt="item.text">
                    </div>
                    <MinLine :count="10"></MinLine>
                    <div class="elem-main-block__text">{{item.middletext}}</div>
                    <MinLine :count="10"></MinLine>
                    <div class="elem-main-block__circle part2__circle">
                      <img :src="item.footerImg" :alt="item.text">
                    </div>
                  </div>
                </div>
                <p class="elem-text">{{item.footertext}}</p>
              </div>
            </el-col>
          </el-row>
        </div>
      </swiper-slide>
      <swiper-slide data-hash="slide3">
        <HomeHeader />
        <div>
          <div>妙寄是一个开放的平台</div>
          <div>快递驿站、社区服务、电商合作、物业合作等均可合作</div>
          <el-row>
            <el-col :span="12">
              
            </el-col>
            <el-col :span="12">

            </el-col>
          </el-row>
        </div>
      </swiper-slide>
      <swiper-slide data-hash="slide4">Slide 4</swiper-slide>
      <swiper-slide data-hash="slide5">Slide 5</swiper-slide>
      <swiper-slide data-hash="slide6">Slide 6</swiper-slide>
      <div class="swiper-pagination swiper-pagination-container" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeHeader from '@/components/HomeHeader.vue'
import MinLine from '@/components/MinLine.vue'

export default {
  name: 'home',
  components: {
    HomeHeader,
    MinLine
  },
  data () {
    return {
      swiperOption: {
        direction: 'vertical',
        autoplay: false,
        hashNavigation: {
          watchState: true,
        },
        pagination: {
          el: '.swiper-pagination-container',
          clickable: true
        }
      },
      part1swiperOption: {
        effect: 'fade',
        loop: true,
        autoplay: true,
        preventClicks: false,
        preventLinksPropagation: false,
        pagination: {
          el: '.swiper-pagination-part1',
          clickable: true
        }
      },
      header: [
        '快递查询',
        '产品体系',
        '快递合作',
        '商务合作',
        '城市合伙人',
        '关于我们',
      ],
      part1Footer: [
        {
          img: require('../assets/images/gongx.png'),
          text: '共配体系',
          hovertitle: '软件+硬件',
          hovertext: [
            '软件：共配sys',
            '硬件：智能高端分拣设配',
          ],
        },
        {
          img: require('../assets/images/moduan.png'),
          text: '末端体系',
          hovertitle: '快递+新零售',
          hovertext: [
            '快递末端：门店+智能快递柜+派送',
            '智能下单：微信+支付宝+电话',
            '新零售：销售+体验+广告+冷链',
          ],
        },
        {
          img: require('../assets/images/fuw.png'),
          text: '服务体系',
          hovertitle: '服务+结算',
          hovertext: [
            '服务：智能客服',
            '结算：网点财务软件',
          ],
        },
        {
          img: require('../assets/images/dians.png'),
          text: '电商体系',
          hovertitle: '平台+商业+培训',
          hovertext: [
            '拼多多、京东',
            '商业：产品销售',
            '培训：电商培训',
          ],
        }
      ],
      part2List: [
        {
          bgImg: require('../assets/images/hom_con.png'),
          text: '连接',
          topImg: require('../assets/images/hom_pac.png'),
          footerImg: require('../assets/images/home_min.png'),
          middletext: '物与人得连接',
          footertext: '妙寄是一种连接节点'
        },
        {
          bgImg: require('../assets/images/hom_ser.png'),
          text: '服务',
          topImg: require('../assets/images/home_min.png'),
          footerImg: require('../assets/images/home_min.png'),
          middletext: '人与人得连接',
          footertext: '妙寄是一种底盘大网'
        },
        {
          bgImg: require('../assets/images/hom_lov.png'),
          text: '关怀',
          topImg: require('../assets/images/hom_hea.png'),
          footerImg: require('../assets/images/hom_hea.png'),
          middletext: '心与心的连接',
          footertext: '妙寄是一种连接节点'
        },
      ]
    } 
  },
}
</script>

<style scoped lang="less">

.home {
  .container {
    width: 100%;
    height: 100vh;
    .part1 {
      header {
        position: absolute;
        top: 40px;
        left: 20%;
        z-index: 9999;
        width: 60%;
      }
      .menu {
        color: white;
        font-size: 12px;
        cursor: pointer;
        .el-col {
          padding-bottom: 10px;
          span {
            padding-bottom: 10px;
          }
          &:hover {
            span {
              border-bottom: 1px solid white; 
            }
          }
        }
      }
      .part1-swiper {
        width: 100%;
        height: 83vh;
        .swiper-slide {
          img {
            width: 100%;
            height: 100%;
          }
        }
        .swiper-pagination-part1 {
          bottom: 10vh;
        }
      }
      .part1-footer {
        position: absolute;
        bottom: 1%;
        left: 19%;
        width: 62%;
        background: white;
        box-shadow: 10px 2px 15px #f5f5f5;
        border-radius: 6px;
        z-index: 9999;
        .el-row {
          height: 24vh;
          .el-col {
            display: flex;
            padding: 10px 0px;
            justify-content:center;
            align-items:Center;
            flex-direction: column;
            font-size: 12px;
            &:hover {
              background: #f9f9f9;
              .tips {
                display: none;
              }
              .hover-tips {
                display: block;
              }
            }
            img {
              height: 50px;
            }
            .tips {
              font-size: 14px;
              padding-top: 26px;
            }
            .hover-tips {
              display: none;
              padding-top: 15px;
              .title {
                color: #e94c1d;
                margin-bottom: 15px;
                span {
                  padding-bottom: 5px;
                  border-bottom: 1px solid #e94c1d;
                }
              }
            }
          }
        }
      }
    }
    .part2 {
      .part2__circle {
        width: 70px;
        height: 70px;
        border-radius: 50%;
        background-color: rgba(245, 236, 236, 0.6);
        line-height: 70px;
        margin-left: 30%;
        display: flex;
        justify-content:center;
        align-items:Center;
        img {
          width: 40px;
        }
      }
      &-main {
        padding: 10vh 10vw 0 10vw;
        .elem {
          &-main {
            height: 400px;
            background: no-repeat;
            background-size: 100% 100%;
            display: flex;
            justify-content:center;
            align-items:Center;
            &:hover {
              .elem-main-circle {
                display: none;
              }
              .elem-main-block {
                display: block;
              }
            }
            &-circle {
              .part2__circle;
              margin-left: 0;
            }
            &-block {
              display: none;
              &__text {
                width: 160px;
                padding: 4px 10px;
                border-radius: 15px;
                font-size: 14px;
                background: rgba(245, 236, 236, 0.6);
              }
            }
          }
          &-text {
            font-size: 14px;
          }
        }
      }
    }
  }
}
</style>