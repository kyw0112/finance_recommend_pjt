<template>
  <div>
    <!-- 페이지 제목 부분. header -->
    <h1>정기예금</h1>
    <hr>
    <!-- 검색 필터, 정렬 기준 선택 부분 -->
    <!-- 검색 필터 선택 부분 -->

    <!-- 선택된 필터 보여주는 부분 -->
    <span v-for="item in searchFilterList" :key="item.content">
      <SelectedSearchFilter
        :search-condition="item.content"
        :is-selected="item.isSelected"
      />
    </span>
    <!-- 정렬 기준 선택 -->

    <!-- 목록 보여주는 부분 -->
    <div v-for="product in baseList" :key="product.fin_prdt_cd">
      <DepositListItem
        :product="product"
      />
    </div>

  </div>
</template>

<script>
import DepositListItem from '@/components/DepositListItem.vue'
import SelectedSearchFilter from '@/components/SelectedSearchFilter.vue'

export default {
  name: 'DepositListView',
  components: {
    DepositListItem,
    SelectedSearchFilter,
  },
  data() {
    return {
      searchFilterList: [
        {
          content: '방문가입',
          isSelected: true,
        },
        {
          content: '온라인가입',
          isSelected: true,
        },
        {
          content: '이자만기지급',
          isSelected: true,
        },
        {
          content: '이자월지급',
          isSelected: true,
        },
        {
          content: '최소예치기간6개월',
          isSelected: true,
        },
        {
          content: '최소예치기간12개월',
          isSelected: true,
        },
      ],
      baseList: [    
        {
            "dcls_month": "202304",
            "fin_co_no": "0010001",
            "fin_prdt_cd": "WR0001B",
            "kor_co_nm": "우리은행",
            "fin_prdt_nm": "WON플러스예금",
            "join_way": "인터넷,스마트폰,전화(텔레뱅킹)",
            "mtrt_int": "만기 후\n- 1개월이내 : 만기시점약정이율×50%\n- 1개월초과 6개월이내: 만기시점약정이율×30%\n- 6개월초과 : 만기시점약정이율×20%\n\n※ 만기시점 약정이율 : 일반정기예금 금리",
            "spcl_cnd": "해당사항 없음",
            "join_deny": "1",
            "join_member": "실명의 개인",
            "etc_note": "- 가입기간: 1~36개월\n- 최소가입금액: 1만원 이상\n- 만기일을 일,월 단위로 자유롭게 선택 가능\n- 만기해지 시 신규일 당시 영업점과 인터넷 홈페이지에 고시된 계약기간별 금리 적용",
            "max_limit": null,
            "dcls_strt_day": "20230504",
            "dcls_end_day": null,
            "fin_co_subm_day": "202305040912"
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010002",
            "fin_prdt_cd": "00320342",
            "kor_co_nm": "한국스탠다드차타드은행",
            "fin_prdt_nm": "e-그린세이브예금",
            "join_way": "인터넷,스마트폰",
            "mtrt_int": "만기 후 1개월: 약정이율의 50%\n만기 후 1개월 초과 1년 이내: 약정이율의 30%\n만기 후 1년 초과: 약정이율의 10%",
            "spcl_cnd": "1.SC제일은행 최초 거래 신규고객에 대하여 우대 이율을 제공함 (보너스이율0.2%)                     2.SC제일마이백통장에서 출금하여 이 예금을 신규하는경우에 보너스이율을 제공함\n(가입기간:1년제/ 보너스이율:0.1% / 만기해약하는 경우에 한해 보너스이율을 적용함)",
            "join_deny": "1",
            "join_member": "개인(개인사업자 포함)",
            "etc_note": "디지털채널 전용상품 (인터넷, 모바일뱅킹)",
            "max_limit": 499999999,
            "dcls_strt_day": "20230420",
            "dcls_end_day": "99991231",
            "fin_co_subm_day": "202304201011"
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010016",
            "fin_prdt_cd": "10511008000996000",
            "kor_co_nm": "대구은행",
            "fin_prdt_nm": "DGB주거래우대예금(첫만남고객형)",
            "join_way": "영업점,인터넷,스마트폰",
            "mtrt_int": "만기 후 1개월 미만 경과 : 약정이자율 x 50%\n만기 후 3개월 미만 경과 : 약정이자율 x 25%\n 만기 후 3개월 이상 경과 : 약정이자율 x 12%",
            "spcl_cnd": "* 최고우대금리 : 0.60%\n              \n - 목돈굴리기예금 최초 가입시 : 0.2%\n - 최근 1개월 이내 신용(체크)카드 신규 발급 시 : 0.2%\n - 최근 1개월 이내 인터넷.폰.스마트뱅킹 가입시 : 0.2%\n -*인터넷/스마트뱅킹을 통해 가입시 우대 : 0.05%",
            "join_deny": "1",
            "join_member": "실명의 개인",
            "etc_note": "계좌당 가입 최저한도 : 100만원",
            "max_limit": null,
            "dcls_strt_day": "20230420",
            "dcls_end_day": null,
            "fin_co_subm_day": "202304200929"
        },
      ],
      optionList: [
        {
            "dcls_month": "202304",
            "fin_co_no": "0010001",
            "fin_prdt_cd": "WR0001B",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "6",
            "intr_rate": 3.35,
            "intr_rate2": 3.35
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010001",
            "fin_prdt_cd": "WR0001B",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "12",
            "intr_rate": 3.47,
            "intr_rate2": 3.47
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010001",
            "fin_prdt_cd": "WR0001B",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "24",
            "intr_rate": 3.3,
            "intr_rate2": 3.3
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010001",
            "fin_prdt_cd": "WR0001B",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "36",
            "intr_rate": 3.28,
            "intr_rate2": 3.28
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010002",
            "fin_prdt_cd": "00320342",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "6",
            "intr_rate": 3.5,
            "intr_rate2": 3.7
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010002",
            "fin_prdt_cd": "00320342",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "12",
            "intr_rate": 3.6,
            "intr_rate2": 3.9
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010016",
            "fin_prdt_cd": "10511008000996000",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "6",
            "intr_rate": 2.46,
            "intr_rate2": 3.11
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010016",
            "fin_prdt_cd": "10511008000996000",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "12",
            "intr_rate": 3.2,
            "intr_rate2": 3.85
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010016",
            "fin_prdt_cd": "10511008000996000",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "24",
            "intr_rate": 3.22,
            "intr_rate2": 3.87
        },
        {
            "dcls_month": "202304",
            "fin_co_no": "0010016",
            "fin_prdt_cd": "10511008000996000",
            "intr_rate_type": "S",
            "intr_rate_type_nm": "단리",
            "save_trm": "36",
            "intr_rate": 3.24,
            "intr_rate2": 3.89
        },
      ]
    }
  },
  // // CORS 때문에 안 됨
  // mounted() {
  //   this.$axios({
  //     method: 'GET',
  //     url: 'http://finlife.fss.or.kr/finlifeapi/depositProductsSearch.json?auth=apikey들어갈부분&topFinGrpNo=020000&pageNo=1'
  //   })
  //   .then((response) => {
  //     this.info = response
  //   })
  // }
}
</script>

<style>

</style>