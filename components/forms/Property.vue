<template>
  <div class="property-info">
    <div class="bg-gray-100 p-8">
      <p class="form-section-name mb-8">Property</p>
      <div class="grid grid-cols-2 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.property.yearBuilt.$error,
            }"
          >
            <label class="form__label"
              >Year Home Built<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="property.yearBuilt"
              v-model="validator.property.yearBuilt.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.property.yearBuilt.$error &&
              !validator.property.yearBuilt.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.property.preProjectArea.$error,
            }"
          >
            <label class="form__label"
              >Pre-Project Home Area (sq. ft.)<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="property.preProjectArea"
              v-model="validator.property.preProjectArea.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.property.preProjectArea.$error &&
              !validator.property.preProjectArea.required
            "
          >
            * Required
          </div>
        </div>
      </div>
      <div class="grid grid-cols-2 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.property.postProjectArea.$error,
            }"
          >
            <label class="form__label"
              >Post-Project Home Area (sq. ft.)<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="property.postProjectArea"
              v-model="validator.property.postProjectArea.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.property.postProjectArea.$error &&
              !validator.property.postProjectArea.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error':
                validator.property.electricPanelUpgraded.$error,
            }"
          >
            <label class="form__label"
              >Was the electric panel upgraded?<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="property.electricPanelUpgraded"
              v-model="validator.property.electricPanelUpgraded.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.property.electricPanelUpgraded.$error &&
              !validator.property.electricPanelUpgraded.required
            "
          >
            * Required
          </div>
        </div>
      </div>
      <div
        class="form-group"
        :class="{
          'form-group--error': validator.property.otherElectricUpgrades.$error,
        }"
      >
        <label class="form__label"
          >Were other electrification upgrades performed?<span class="r"
            >*</span
          ></label
        >
        <input
          class="form__input"
          type="text"
          name="property.otherElectricUpgrades"
          v-model="validator.property.otherElectricUpgrades.$model"
        />
      </div>
      <div
        class="error"
        v-if="
          validator.property.otherElectricUpgrades.$error &&
          !validator.property.otherElectricUpgrades.required
        "
      >
        * Required
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['property', 'validator'],
}
</script>
