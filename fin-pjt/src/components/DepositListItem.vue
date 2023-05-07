<template>
  <!-- <div class="container">
    <div class="card mb-3">
      <div class="row g-0">
        <div class="col-md-4">
          <img src="" class="img-fluid rounded-start" alt="...">
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h5 class="card-title">{{ product.fin_prdt_nm }}</h5>
            <p class="card-text">{{ product.kor_co_nm }}</p>
            <p class="card-text">{{ product.mtrt_int }}</p>
            <p class="card-text">{{ product.join_way }}</p>
            <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
          </div>
        </div>
      </div>
    </div>
  </div> -->
  <div class="mb-1">
    <b-card no-body class="overflow-hidden">
      <b-row no-gutters>
        <b-col md="3">
          <b-card-img src="https://picsum.photos/400/400/?image=20" alt="Image" rounded="circle"></b-card-img>
        </b-col>
        <b-col md="9">
          <b-card-body :title="product.fin_prdt_nm">
            <hr>
            <b-card-text>
              {{ product.kor_co_nm }}
            </b-card-text>
            <b-card-text>
              {{ product.mtrt_int }}
            </b-card-text>
            <b-card-text>
              {{ product.join_way }}
            </b-card-text>
          </b-card-body>
        </b-col>
      </b-row>
    </b-card>
  </div>  
</template>

<script>
export default {
  name: 'DepositListItem',
  props: {
    product: Object,
  }
}
</script>

<style>

</style>