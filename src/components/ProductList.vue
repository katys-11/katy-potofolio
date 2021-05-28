<template>
  <div>
    <v-row>
      <product
        v-for="(product, key) in filterdList"
        :key="key"
        :product="product"
      >
      </product
    ></v-row>
  </div>
</template>

<script>
import Product from "./Product.vue";
export default {
  name: "ProductList",
  components: { Product },
  data: () => ({
    sortYear: "全て",
    products: [
      {
        id: 1,
        name: "富戸ブルーブランドプロモーション",
        // TODO: ここに差し替えたい画像のパスを入れてね
        image: require("@/assets/re-vr.png"),
        year: "2020",
        category: "プロジェクト",
        use: "地域活性化、ブランディング、AR、",
        urls: [
          // TODO: ここにリンクしたいURLを入れてね
          "https://www.meisei-u.ac.jp/2021/2021031504.html",
        ],
      },
      {
        id: 1,
        name: "ウズベキスタンプロモーション",
        // TODO: ここに差し替えたい画像のパスを入れてね
        image: require("@/assets/2019pm.jpeg"),
        year: "2019",
        category: "プロジェクト",
        use: "プロジェクションマッピング、英語プレゼンテーション",
        urls: [
          // TODO: ここにリンクしたいURLを入れてね
          "https://www.meisei-u.ac.jp/2020/20200120p1.html",
        ],
      },
      {
        id: 1,
        name: "ダンス",
        // TODO: ここに差し替えたい画像のパスを入れてね
        image: require("@/assets/2019pm.jpeg"),
        year: "2019",
        category: "作品",
        use: "受賞歴、振り付け",
        urls: [
          // TODO: ここにリンクしたいURLを入れてね
          "https://www.meisei-u.ac.jp/2020/20200120p1.html",
        ],
      },
      {
        id: 1,
        name: "論文",
        // TODO: ここに差し替えたい画像のパスを入れてね
        image: require("@/assets/2019pm.jpeg"),
        year: "2020",
        category: "研究",
        use: "英語論文、ブラジル学会",
        urls: [
          // TODO: ここにリンクしたいURLを入れてね
          "https://www.meisei-u.ac.jp/2020/20200120p1.html",
        ],
      },
    ],
  }),
  computed: {
    filterdList: function () {
      const newList = [];
      for (let i = 0; i < this.products.length; i++) {
        if (this.sortYear === "2020" && this.products[i].year === "2020") {
          newList.push(this.products[i]);
        } else if (
          this.sortYear === "2019" &&
          this.products[i].year === "2019"
        ) {
          newList.push(this.products[i]);
        } else if (
          this.sortYear === "2018" &&
          this.products[i].year === "2018"
        ) {
          newList.push(this.products[i]);
        } else if (this.sortYear === "全て") {
          newList.push(this.products[i]);
        }
      }
      return newList;
    },
  },
  methods: {
    sortYearChanged: function (year) {
      console.log(year);
      this.sortYear = year;
    },
  },
};
</script>
