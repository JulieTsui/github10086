<style lang="less">
@import url('../assets/style/variable.less');

.page-links { width: 100%; min-width: 1280px; height: 100%; padding: 1px; font-family: 'Avenir', Helvetica, Arial, sans-serif; -webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale; color: #2c3e50; position: absolute; top: 0; left: 0; overflow-x: scroll;
  .app-bg { width: 100%; height: 100%; position: absolute; top: 0; left: 0; z-index: -100; opacity: 0.5; background-size: cover; background-repeat: no-repeat; transition: all .5s linear; }
  .app-content { width: 100%; height: 100%; overflow-y: scroll; position: relative;

    .links-wrap { width: 1100px; margin: 50px auto; border-radius: 5px; overflow: hidden;
      .left-section { width: 70%; min-height: 450px; padding: 14px 0 0 16px; float: left; background: rgba(255, 255, 255, .5);
        h2 { color: @c-blue; font-weight: 400; font-size: 22px; }
        dl.links-list { padding: 20px 0;
          .link-item { width: 230px; float: left; padding: 3px 10px; margin: 0 5px 15px 0;
            dt { font-weight: 400; font-size: 16px;
              a { display: inline-block; border-bottom: solid 1px @c-red; }
              a:hover { color: @c-red; }
            }
            dd { margin-top: 7px; color: #555; font-size: 13px; }
          }
          .textclip { overflow: hidden; white-space: nowrap; text-overflow: ellipsis; }
        }
      }
      .right-section { width: 30%; min-height: 450px; padding: 13px 0 0 15px; float: left; background: rgba(255, 255, 255, .8);
        .info { margin: 0 10px 20px 0;
          h2 { margin: 5px 0 10px; border-left: 3px solid @c-blue; text-indent: 10px; font-size: 16px; }
          li { list-style: circle inside; font-size: 14px; line-height: 23px; color: #000; user-select: text; }
          span { font-size: 13px; color: #555; user-select: text; }
        }
      }
    }
  }
}
</style>

<template>
  <div class="page-links">
    <div class="app-bg" :style="appBgStyle"></div>
    <div class="app-content clearfix">
      <PageHeader></PageHeader>
      <div class="links-wrap responsive-section-a clearfix">
        <section class="left-section">
          <h2 class="links-title">????????????</h2>
          <dl class="links-list clearfix">
            <div class="link-item" v-for="(item, index) in Links" :key="index">
              <dt class="textclip"><a :href="item.url" target="_blank">{{ item.title }}</a></dt>
              <dd class="textclip">{{ item.desc }}</dd>
            </div>
          </dl>
        </section>

        <section class="right-section">
          <div class="info site-info">
            <h2>????????????</h2>
            <ul>
              <li>?????????<span>???????????? - AutoPiano</span></li>
              <li>?????????<span>http://www.autopiano.cn</span></li>
              <li>?????????<span>???????????? ???????????????????????????</span></li>
            </ul>
          </div>
          <div class="info exchange-info">
            <h2>????????????????????????</h2>
            <ul>
              <li>????????????????????????????????????????????????</li>
              <li>???????????????<span>?????????????????????AutoPiano?????????</span></li>
              <li>???????????????<span>????????????????????????3??????</span></li>
              <li>???????????????<span>IT??????????????????????????????????????????????????????PASS</span></li>
              <li>???????????????<span>???????????????????????????IP??????PV???????????????</span></li>
              <li>?????????<span>??????????????????????????????????????????????????????????????????????????????????????????????????????????????????????????????</span></li>
            </ul>
          </div>
        </section>
      </div>
      <div class="blank-page-links" style="height: 80px;"></div>
      <PageFooter></PageFooter>
    </div>
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader'
import PageFooter from '@/components/Footer'

import { mapActions, mapGetters } from 'vuex'
import { Links, Wallpaper } from '@/config'

export default {
  name: '',
  components: {
    PageHeader,
    PageFooter
  },
  mixins: [],
  props: [],
  data() {
    return {
      Links
    }
  },
  computed: {
		...mapGetters([
			'$currentWallpaper'
    ]),
    appBgStyle() {
      return `background-image: url(${this.$currentWallpaper});`
    }
  },
  mounted() {
  },
  watch: {},
  methods: {}
}
</script>
