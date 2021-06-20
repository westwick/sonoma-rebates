<template>
  <div class="mailing-address">
    <div class="bg-gray-100 p-8">
      <p class="form-section-name mb-8">
        Service Address For Installed Equipment
      </p>
      <div
        class="form-group"
        :class="{
          'form-group--error': validator.serviceAddress.street.$error,
        }"
      >
        <label class="form__label"
          >Street Address<span class="r">*</span></label
        >
        <input
          class="form__input"
          type="text"
          name="serviceAddress.street"
          v-model="validator.serviceAddress.street.$model"
        />
      </div>
      <div
        class="error"
        v-if="
          validator.serviceAddress.street.$error &&
          !validator.serviceAddress.street.required
        "
      >
        * Required
      </div>
      <div class="grid grid-cols-3 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.serviceAddress.city.$error,
            }"
          >
            <label class="form__label">City<span class="r">*</span></label>
            <input
              class="form__input"
              type="text"
              name="serviceAddress.city"
              v-model="validator.serviceAddress.city.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.serviceAddress.city.$error &&
              !validator.serviceAddress.city.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.serviceAddress.state.$error,
            }"
          >
            <label class="form__label">State<span class="r">*</span></label>
            <input
              class="form__input"
              type="text"
              name="serviceAddress.state"
              v-model="validator.serviceAddress.state.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.serviceAddress.state.$error &&
              !validator.serviceAddress.state.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.serviceAddress.zip.$error,
            }"
          >
            <label class="form__label">Zip<span class="r">*</span></label>
            <input
              class="form__input"
              type="text"
              name="serviceAddress.zip"
              v-model="validator.serviceAddress.zip.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.serviceAddress.zip.$error &&
              !validator.serviceAddress.zip.required
            "
          >
            * Required
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['serviceAddress', 'validator'],
}
</script>
