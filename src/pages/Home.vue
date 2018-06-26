<template>
  <v-ons-page>
    <v-ons-toolbar class="home-toolbar">
      <div class="center">{{ msg }}</div>
    </v-ons-toolbar>

    <div class="header" style="margin:1%;">
      <img src="../assets/Vso59x2r_400x400.jpg" alt="logo">
    </div>

    <div style="text-align: center;margin:0;">
      <p v-if="isShow===false">「Start」ボタンを押してください</p>
      <p v-else>「Stop」ボタンを押してください</p>
    </div>
    <div style="text-align: center;margin: 3% 0;">
      <button @click="start()" style="margin: 6px 10px;font-size:14px;">Start</button>
      <button @click="stop()" style="margin: 6px 10px;font-size:14px;">Stop</button>
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
      ],
      city: [
        [
          '札幌市',
          '函館市',
          '小樽市',
          '旭川市',
          '室蘭市',
          '釧路市',
          '帯広市',
          '北見市',
          '夕張市',
          '岩見沢市',
          '網走市',
          '留萌市',
          '苫小牧市',
          '稚内市',
          '美唄市',
          '芦別市',
          '江別市',
          '赤平市',
          '紋別市',
          '士別市',
          '名寄市',
          '三笠市',
          '根室市',
          '千歳市',
          '滝川市',
          '砂川市',
          '歌志内市',
          '深川市',
          '富良野市',
          '登別市',
          '恵庭市',
          '伊達市',
          '北広島市',
          '石狩市',
          '北斗市',
          '当別町',
          '新篠津村',
          '松前町',
          '福島町',
          '知内町',
          '木古内町',
          '七飯町',
          '鹿部町',
          '森町',
          '八雲町',
          '長万部町',
          '江差町',
          '上ノ国町',
          '厚沢部町',
          '乙部町',
          '奥尻町',
          '今金町',
          'せたな町',
          '島牧村',
          '寿都町',
          '黒松内町',
          '蘭越町',
          'ニセコ町',
          '真狩村',
          '留寿都村',
          '喜茂別町',
          '京極町',
          '倶知安町',
          '共和町',
          '岩内町',
          '泊村',
          '神恵内村',
          '積丹町',
          '古平町',
          '仁木町',
          '余市町',
          '赤井川村',
          '南幌町',
          '奈井江町',
          '上砂川町',
          '由仁町',
          '長沼町',
          '栗山町',
          '月形町',
          '浦臼町',
          '新十津川町',
          '妹背牛町',
          '秩父別町',
          '雨竜町',
          '北竜町',
          '沼田町',
          '鷹栖町',
          '東神楽町',
          '当麻町',
          '比布町',
          '愛別町',
          '上川町',
          '東川町',
          '美瑛町',
          '上富良野町',
          '中富良野町',
          '南富良野町',
          '占冠村',
          '和寒町',
          '剣淵町',
          '下川町',
          '美深町',
          '音威子府村',
          '中川町',
          '幌加内町',
          '増毛町',
          '小平町',
          '苫前町',
          '羽幌町',
          '初山別村',
          '遠別町',
          '天塩町',
          '猿払村',
          '浜頓別町',
          '中頓別町',
          '枝幸町',
          '豊富町',
          '礼文町',
          '利尻町',
          '利尻富士町',
          '幌延町',
          '美幌町',
          '津別町',
          '斜里町',
          '清里町',
          '小清水町',
          '訓子府町',
          '置戸町',
          '佐呂間町',
          '遠軽町',
          '湧別町',
          '滝上町',
          '興部町',
          '西興部村',
          '雄武町',
          '大空町',
          '豊浦町',
          '壮瞥町',
          '白老町',
          '厚真町',
          '洞爺湖町',
          '安平町',
          'むかわ町',
          '日高町',
          '平取町',
          '新冠町',
          '浦河町',
          '様似町',
          'えりも町',
          '新ひだか町',
          '音更町',
          '士幌町',
          '上士幌町',
          '鹿追町',
          '新得町',
          '清水町',
          '芽室町',
          '中札内村',
          '更別村',
          '大樹町',
          '広尾町',
          '幕別町',
          '池田町',
          '豊頃町',
          '本別町',
          '足寄町',
          '陸別町',
          '浦幌町',
          '釧路町',
          '厚岸町',
          '浜中町',
          '標茶町',
          '弟子屈町',
          '鶴居村',
          '白糠町',
          '別海町',
          '中標津町',
          '標津町',
          '羅臼町'
        ],
        [
          '青森市',
          '弘前市',
          '八戸市',
          '黒石市',
          '五所川原市',
          '十和田市',
          '三沢市',
          'むつ市',
          'つがる市',
          '平川市',
          '平内町',
          '今別町',
          '蓬田村',
          '外ヶ浜町',
          '鰺ヶ沢町',
          '深浦町',
          '西目屋村',
          '藤崎町',
          '大鰐町',
          '田舎館村',
          '板柳町',
          '鶴田町',
          '中泊町',
          '野辺地町',
          '七戸町',
          '六戸町',
          '横浜町',
          '東北町',
          '六ヶ所村',
          'おいらせ町',
          '大間町',
          '東通村',
          '風間浦村',
          '佐井村',
          '三戸町',
          '五戸町',
          '田子町',
          '南部町',
          '階上町',
          '新郷村'
        ],
        [

        ]
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
