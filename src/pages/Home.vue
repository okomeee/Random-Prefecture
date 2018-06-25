<template>
  <v-ons-page>
    <v-ons-toolbar class="home-toolbar">
      <div class="center">{{ msg }}</div>
    </v-ons-toolbar>

    <div class="header" style="margin:1%;">
      <img src="../assets/onsenui-logo.png" alt="vue-logo">
    </div>

    <div style="text-align: center;margin:0;">
      <p v-if="isShow===false">「Start」ボタンを押してください</p>
      <p v-else>「Stop」ボタンを押してください</p>
    </div>
    <div style="text-align: center;margin: 3% 0;">
      <button @click="start()" style="margin: 6px 10px;font-size:24px;">Start</button>
      <button @click="stop()" style="margin: 6px 10px;font-size:24px;">Stop</button>
    </div>
    <div style="text-align: center;margin:10% 0;">
      <p id="prefecture" style="font-size:32px;"></p>
    </div>

  </v-ons-page>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      msg: 'Random Prefecture',
      isShow: false,
      prefectures: [
        '北海道',
        '青森県',
        '岩手県',
        '宮城県',
        '秋田県',
        '山形県',
        '福島県',
        '茨城県',
        '栃木県',
        '群馬県',
        '埼玉県',
        '千葉県',
        '東京都',
        '神奈川県',
        '新潟県',
        '富山県',
        '石川県',
        '福井県',
        '山梨県',
        '長野県',
        '岐阜県',
        '静岡県',
        '愛知県',
        '三重県',
        '滋賀県',
        '京都府',
        '大阪府',
        '兵庫県',
        '奈良県',
        '和歌山県',
        '鳥取県',
        '島根県',
        '岡山県',
        '広島県',
        '山口県',
        '徳島県',
        '香川県',
        '愛媛県',
        '高知県',
        '福岡県',
        '佐賀県',
        '長崎県',
        '熊本県',
        '大分県',
        '宮崎県',
        '鹿児島県',
        '沖縄県'
      ]
    }
  },
  methods: {
    getRandomIntInclusive (min, max) {
      min = Math.ceil(min)
      max = Math.floor(max)
      return Math.floor(Math.random() * (max - min + 1)) + min
    },
    start () {
      this.isShow = true
      setInterval(() => {
        if (this.isShow) {
          document.getElementById('prefecture').innerHTML = this.prefectures[this.getRandomIntInclusive(0, 46)]
        }
      }, 50)
    },
    stop () {
      this.isShow = false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  text-align: center;
}

img {
  max-width: 300px;
}

ons-list-title {
  text-transform: none;
}

ons-list-title:not(:first-of-type) {
  margin-top: 30px;
}

ons-card {
  text-align: center;
}

ons-list-item, ons-card {
  cursor: pointer;
}
</style>
