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
      <div class="grid grid-cols-1 md:grid-cols-3 gap-x-8">
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
            <select
              class="form__input"
              v-model="validator.serviceAddress.state.$model"
              required
            >
              <option value="" default selected hidden>Select Any</option>
              <option value="AL">AL</option>
              <option value="AK">AK</option>
              <option value="AZ">AZ</option>
              <option value="AR">AR</option>
              <option value="CA">CA</option>
              <option value="CO">CO</option>
              <option value="CT">CT</option>
              <option value="DE">DE</option>
              <option value="DC">DC</option>
              <option value="FL">FL</option>
              <option value="GA">GA</option>
              <option value="HI">HI</option>
              <option value="ID">ID</option>
              <option value="IL">IL</option>
              <option value="IN">IN</option>
              <option value="IA">IA</option>
              <option value="KS">KS</option>
              <option value="KY">KY</option>
              <option value="LA">LA</option>
              <option value="ME">ME</option>
              <option value="MD">MD</option>
              <option value="MA">MA</option>
              <option value="MI">MI</option>
              <option value="MN">MN</option>
              <option value="MS">MS</option>
              <option value="MO">MO</option>
              <option value="MT">MT</option>
              <option value="NE">NE</option>
              <option value="NV">NV</option>
              <option value="NH">NH</option>
              <option value="NJ">NJ</option>
              <option value="NM">NM</option>
              <option value="NY">NY</option>
              <option value="NC">NC</option>
              <option value="ND">ND</option>
              <option value="OH">OH</option>
              <option value="OK">OK</option>
              <option value="OR">OR</option>
              <option value="PA">PA</option>
              <option value="RI">RI</option>
              <option value="SC">SC</option>
              <option value="SD">SD</option>
              <option value="TN">TN</option>
              <option value="TX">TX</option>
              <option value="UT">UT</option>
              <option value="VT">VT</option>
              <option value="VA">VA</option>
              <option value="WA">WA</option>
              <option value="WV">WV</option>
              <option value="WI">WI</option>
              <option value="WY">WY</option>
            </select>
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
            <label class="form__label">ZIP code<span class="r">*</span></label>
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
  methods: {
    toggleSameAs(e) {
      this.$emit('sameAs', e.target.checked)
    },
  },
}
</script>
