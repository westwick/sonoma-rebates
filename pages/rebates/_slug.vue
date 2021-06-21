<template>
  <div class="product-page">
    <div class="product-hero">
      <div class="grid grid-cols-2">
        <div class="product-hero-info-container">
          <div class="product-hero-info">
            <p class="text-rebates">Rebates</p>
            <p class="text-product-title">
              {{ page.name }}: Save up to {{ page.maxSavings }}
            </p>
          </div>
        </div>
        <div class="product-hero-img"></div>
      </div>
    </div>
    <div class="product-main">
      <div class="product-main-container">
        <div class="container mx-auto">
          <div class="grid grid-cols-12">
            <div class="product-img col-span-4 bg-white">
              <img
                class="mx-auto mt-8"
                :src="require(`~/assets/images/${page.image}`)"
              />
            </div>
            <div class="product-info col-span-5 bg-white pr-20">
              <h2 class="product-headline">{{ page.headline }}</h2>
              <p class="text-lg">{{ page.productInfo }}</p>
            </div>
            <div class="product-apply-now col-span-3 bg-gray-100">
              <p class="how-to-apply mb-4">HOW TO APPLY</p>
              <p class="font-bold">Step 1</p>
              <p class="mb-8">
                Review the rebate qualifications and details below.
              </p>
              <p class="font-bold">Step 2</p>
              <p class="mb-8">Have the required documents ready.</p>
              <p class="font-bold">Step 3</p>
              <p class="mb-8">Complete the online application form.</p>
              <NuxtLink to="/apply" class="button-cta">Apply Now</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="product-tabs">
      <div class="product-tabs-container container mx-auto">
        <div class="tabs-group">
          <div
            class="tab product-tab product-qualifications"
            :class="{ 'tab-active': tab1active }"
            @click="setTab('qualifications')"
          >
            Qualifications
          </div>
          <div
            class="tab product-tab product-documents"
            :class="{ 'tab-active': !tab1active }"
            @click="setTab('documents')"
          >
            Documents
          </div>
        </div>
        <div
          class="product-qualifications-text"
          v-if="tab === 'qualifications'"
        >
          <h1>Qualifications</h1>
          <h2>Please be ready to provide the following information:</h2>
          <p v-for="qual in page.qualifications" :key="qual">
            <img src="~/assets/images/checkbox-icon.svg" />
            {{ qual }}
          </p>
        </div>
        <div class="product-qualifications-text" v-if="tab === 'documents'">
          <h1>Documents</h1>
          <h2>Please be ready to provide the following information:</h2>
          <ul class="list-disc">
            <li v-for="doc in page.documents" :key="doc">
              {{ doc }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    const slug = params.slug
    const page = await $content('products/' + slug).fetch()

    return {
      page,
    }
  },
  data() {
    return {
      tab: 'qualifications',
    }
  },
  computed: {
    tab1active: function () {
      return this.tab === 'qualifications'
    },
  },
  methods: {
    setTab(tab) {
      this.tab = tab
    },
  },
}
</script>

<style>
@import url('~/assets/css/tabs.css');
.tabs-group {
  margin-bottom: 48px;
}

.product-hero-info-container {
  background: #382658;
  color: #fff;
  padding: 128px 0 184px;
}
.product-hero-info {
  width: 536px;
  margin: 0 auto;
  padding-left: 48px;
}
.product-hero-img {
  background: url('~/assets/images/product-hero.jpg') no-repeat top center;
}
.text-rebates {
  text-transform: uppercase;
  font-size: 16px;
  font-weight: 600;
}
.text-product-title {
  font-size: 40px;
  font-weight: bold;
}

.product-main-container {
  margin-top: -64px;
}
.product-headline {
  font-size: 40px;
  color: #382658;
  margin-top: 56px;
  margin-bottom: 32px;
  font-weight: bold;
}
.product-apply-now {
  padding: 40px;
}
.how-to-apply {
  color: #4f5263;
  font-weight: bold;
  margin-top: 16px;
}

.product-tabs-container {
  border-top: 2px solid #f2f4f6;
  padding-top: 48px;
  padding-bottom: 48px;
}
.product-qualifications-text h1 {
  font-size: 36px;
  font-weight: bold;
  color: #382658;
}
.product-qualifications-text h2 {
  font-size: 26px;
  font-weight: bold;
  color: #4f5263;
  margin-top: 8px;
  margin-bottom: 24px;
}
.product-qualifications-text p {
  font-size: 20px;
  margin-bottom: 16px;
}
.product-qualifications-text p img {
  display: inline;
  margin-right: 48px;
}
</style>
