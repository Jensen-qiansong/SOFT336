<template>
  <dl class="m-sum-card">
    <dt>
      <!-- <h1>{{ meta.name }}</h1> -->
      <h1>LONDON</h1>
      <el-rate
        v-model="rate"
        disabled />
      <span>{{ Number(meta.biz_ext)||rate }}branch</span>
      <span>Per capita $ {{ Number(meta.biz_ext) }}</span>
      <ul>
        <li @click="openMap(meta.location)">dress：LONDONASDFGHASDFGH</li>
        <!-- <li @click="openMap(meta.location)">dress：{{ meta.address }}</li> -->
        <li>phone: {{ meta.tel }}</li>
      </ul>
    </dt>
    <dd>
      <el-carousel
        height="214px"
        indicator-position="none">
        <el-carousel-item
          v-for="(item,idx) in meta.photos"
          :key="idx">
          <h3><img
            :src="item.url"
            alt="item.title"
            width="100%"
            height="100%"></h3>
        </el-carousel-item>
      </el-carousel>
    </dd>
  </dl>
</template>

<script>
export default {
  props: {
    meta: {
      type:Object,
      default:()=>{
        return {}
      }
    }
  },
  data() {
    return {
      sale: 70 + Math.floor(Math.random() * 300)
    }
  },
  computed: {
    rate: function () {
      return Number(this.meta.biz_ext) || Math.floor(Math.random() * 5)
    }
  },
  methods: {
    /* openMap: function (location) {
    } */
  }
}
</script>
