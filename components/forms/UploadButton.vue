<template>
  <div class="file-upload-button">
    <input type="hidden" v-model="inputVal" />
    <div v-if="value" class="uploaded-wrap">
      <p class="uploaded-file-name">{{ displayName }}</p>
      <p><a href="#remove" @click.prevent="clearValue()">Remove</a></p>
    </div>
    <div v-else>
      <button class="upload-button" @click.prevent="uploadDoc()">
        Upload Document
      </button>
    </div>
  </div>
</template>

<script>
import Robodog from '@uppy/robodog'

export default {
  props: ['value', 'uploadPath'],
  computed: {
    inputVal: {
      get() {
        return this.value
      },
      set(val) {
        this.$emit('input', val)
      },
    },
    displayName() {
      // returns string like "longfilenameabc...xyz.jpg"
      return this.value && this.value.length > 30
        ? `${this.value.substring(0, 14)}...${this.value.substring(
            this.value.length - 14
          )}`
        : this.value
    },
  },
  methods: {
    clearValue() {
      this.$emit('input', '')
    },
    uploadDoc() {
      const resultPromise = Robodog.pick({
        target: 'body',
        params: {
          auth: { key: '5314f85b82984dce8d0194ac88be17e3' },
          template_id: '4a6598acae9342228925ffbbc7f6b243',
          fields: {
            path: this.uploadPath || 'noaccountnum',
          },
        },
      })
      resultPromise.then(({ successful }) => {
        if (successful && successful[0]) {
          this.$emit('input', successful[0].name)
        }
      })
    },
  },
}
</script>

<style>
.file-upload-button {
  margin-top: -8px;
  margin-bottom: 24px;
}
.file-upload-button a {
  color: #40cade;
}
.upload-button {
  width: 100%;
  background: #aaa;
  background-image: linear-gradient(to bottom, #fff, #f1f3f6);
  border: 1px solid #c5d1e6;
  height: 48px;
  font-size: 15px;
  max-width: 640px;
}
.uploaded-wrap {
  height: 48px;
  font-size: 16px;
}
.uploaded-file-name {
  color: #9f9f9f;
}
</style>
