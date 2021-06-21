<template>
  <div class="heatpump-info">
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.dateInstalled.$error,
          }"
        >
          <label class="form__label"
            >Date Installed<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.dateInstalled"
            v-model="validator.heatpump.dateInstalled.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.dateInstalled.$error &&
            !validator.heatpump.dateInstalled.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.existingFuelType.$error,
          }"
        >
          <label class="form__label"
            >Existing Heating System Fuel Type<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.existingFuelType"
            v-model="validator.heatpump.existingFuelType.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.existingFuelType.$error &&
            !validator.heatpump.existingFuelType.required
          "
        >
          * Required
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['heatpump', 'validator'],
}
</script>
