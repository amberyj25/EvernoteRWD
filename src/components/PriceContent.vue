<template>
  <div class="price_content">
    <div class="price_content_row">
      <div
        :class="priceList.outer_style"
        v-for="(priceList, index) in priceContent"
        :key="index"
      >
        <img
          class="priceList_icon"
          :src="priceList.icon"
          alt="icon"
        />
        <h5 :class="priceList.program_style" class="price_content_title">
          {{ priceList.title }}
        </h5>
        <div class="price_outer">
          <h6 class="price">
            <span class="price_money">{{ priceList.price }}</span>
            <span class="price_unit">{{ priceList.unit }}</span>
          </h6>
          <i class="fas fa-arrow-circle-down" @click="changeDropdownStatus(priceList)"></i>
        </div>
        <p class="note">{{ priceList.little_title }}</p>
        <div :class="priceList.drop_down_status">
          <div
            class="priceList_content"
            v-for="(list, index) in priceList.content"
            :key="index"
          >
            <i class="fas fa-check priceList_content_icon_tick"></i>
            <span class="price_content_text">{{ list }}</span>
          </div>
        </div>
        <a :class="[priceList.btn,priceList.drop_down_status]" class="priceList_btn" href="##">
          {{ priceList.btn_text }}
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'PriceContent',
  data() {
    return {
      priceContent: [
        {
          id: 0,
          icon:'https://evernote.com/c/assets/compare-plans/basic-simple.svg?93a8ae61aaa41ee1',
          title: '入門版',
          price: '免費',
          unit: '',
          little_title: '寫下最佳記事。',
          content: [
            '最多可同步兩個裝置',
            '利用搜尋和標籤，快速找到記事',
            '在您的記事上套用豐富格式',
            '擷取網頁',
            '記事大小限制 25MB',
            '每月上載限額 60MB',
          ],
          btn_text: '立刻開始',
          outer_style: {
            is_price_list_content_all: true,
            is_price_list_left: true,
          },
          program_style: 'price_content_title_left',
          btn: 'price_content_btn_left',
          is_change_list_status: true,
          drop_down_status: 'no_drop_down_class_rwd',
        },
        {
          id: 1,
          icon: 'https://evernote.com/c/assets/compare-plans/premium-simple.svg?2cb08b002af6e56e',
          title: '專業版',
          price: 'NT$150.00',
          unit: '/ 月',
          little_title: '提高生產力。',
          content: [
            '入門版的所有功能',
            '同步裝置數不限',
            '離線存取記事',
            '標註 PDF 檔',
            '可搜尋 Office 文件和 PDF 檔內的文字',
            '建立自訂範本',
            '記事大小上限 200MB',
            '每月上載限額 10GB',
          ],
          btn_text: '免費試用',
          outer_style: {
            is_price_list_content_all: true,
            is_price_list_center: true,
          },
          program_style: 'price_content_title_center',
          btn: 'price_content_btn_center',
          is_change_list_status: true,
          drop_down_status: 'no_drop_down_class_rwd',
        },
        {
          id: 2,
          icon: 'https://evernote.com/c/assets/compare-plans/business-simple.svg?960826d59e449ab2',
          title: '企業版',
          price: 'NT$360.00',
          unit: '/ 使用者 / 月',
          little_title: '可全公司共同協作。',
          content: [
            '專業版的所有功能',
            '在共用空間裡共同協作',
            '查看團隊的動態歷史記錄',
            '集中化帳戶管理',
            '管理團隊資料和存取權',
            '使用單一登入 (SSO) 快速登入',
            '企業資料擁有權',
            '20GB 的每月上載限額 + 每位使用者個別上載限額 2GB',
          ],
          btn_text: '免費試用',
          outer_style: {
            is_price_list_content_all: true,
            is_price_list_right: true,
          },
          program_style: 'price_content_title_right',
          btn: 'price_content_btn_right',
          is_change_list_status: true,
          drop_down_status: 'no_drop_down_class_rwd',
        },
      ]
    };
  },
  methods: {
    changeDropdownStatus(priceList) {
      if(!priceList.is_change_list_status) {
        priceList.drop_down_status = 'no_drop_down_class_rwd';
        priceList.is_change_list_status = true;
        return;
      }

      priceList.drop_down_status = 'drop_down_class_rwd';
      priceList.is_change_list_status = false;
    }
  }
};
</script>
<style scoped>
.price_content_row {
  display: flex;
  justify-content: space-between;
}
.note {
  font-size: 0.8rem;
}
.priceList_content {
  margin: 15px 0;
}
.priceList_content_icon_tick {
  width: 25px;
  vertical-align: middle;
}
.price_content_text {
  font-size: 1rem;
}
.is_price_list_content_all {
  max-width: 350px;
  height: fit-content;
  padding: 15px 25px;
  border-radius: 5px;
}
.is_price_list_left {
  border: 2px solid black;
}
.is_price_list_center {
  border: 2px solid #00a82d;
  margin: 0 25px;
}
.is_price_list_right {
  border: 2px solid black;
}
.priceList_icon {
  width: 25px;
  height: 25px;
  vertical-align: middle;
}
.price_content_title {
  display: inline-block;
  vertical-align: middle;
  font-size: 1.5rem;
}
.price_content_title_left {
  color: #666666;
}
.price_content_title_center {
  color: #00a82d;
}
.price_content_title_right {
  color: black;
}
.price {
  margin: 5px 0;
}
.price_money {
  font-size: 2.5rem;
}
.price_unit {
  font-size: 0.5rem;
}
.fa-arrow-circle-down {
  display: none;
}
.priceList_btn {
  display: block;
  padding: 15px 0;
  border-radius: 5px;
  text-align: center;
}
.price_content_btn_left {
  border: 2px solid #666666;
  color: #666666;
}
.price_content_btn_center {
  color: white;
  background: #00a82d;
}
.price_content_btn_right {
  color: white;
  background: black;
}
@media (max-width:770px) {
  .price_content_row {
    flex-wrap: wrap;
    justify-content: center;
  }
  .is_price_list_content_all {
    width: 100%;
    max-width: 580px;
    margin: 25px 0;
  }
  .is_price_list_center {
    margin: 0;
  }
  .price_outer {
    display: flex;
    justify-content: space-between;
  }
  .fa-arrow-circle-down {
    display: inline-block;
    font-size: 2rem;
  }
  .drop_down_class_rwd {
    display: block;
  }
  .no_drop_down_class_rwd {
    display: none;
  }
}
@media (max-width:770px) {
  .is_price_list_content_all {
    min-width: 200px;
  }
}
@media (max-width:450px) {
  .price_money {
    font-size: 1.5rem;
  }
  .fa-arrow-circle-down {
    font-size: 1.5rem;
    line-height: 43px;
  }
}
</style>