<template>
  <div class="customer-details">
    <div class="bg-gray-100 p-8">
      <p class="form-section-name mb-8">Account Information</p>
      <div class="grid grid-cols-2 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.pgeAccountNum.$error,
            }"
          >
            <label class="form__label"
              >PG&amp;E Account #<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.pgeAccountNum"
              v-model="validator.account.pgeAccountNum.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.pgeAccountNum.$error &&
              !validator.account.pgeAccountNum.required
            "
          >
            * Required
          </div>

          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.pgeGasSAID.$error,
            }"
          >
            <label class="form__label"
              >PG&amp;E Gas SAID<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.pgeGasSAID"
              v-model="validator.account.pgeGasSAID.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.pgeGasSAID.$error &&
              !validator.account.pgeGasSAID.required
            "
          >
            * Required
          </div>

          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.customerPhone.$error,
            }"
          >
            <label class="form__label"
              >Customer Phone Number<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="number"
              name="account.customerPhone"
              v-model="validator.account.customerPhone.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.customerPhone.$error &&
              !validator.account.customerPhone.required
            "
          >
            * Required
          </div>

          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.language.$error,
            }"
          >
            <label class="form__label"
              >Primary Language<span class="r">*</span></label
            >
            <select
              class="form__input"
              name="account.language"
              v-model="validator.account.language.$model"
              required
            >
              <option value="" default selected hidden>Select Any</option>
              <option value="English">English</option>
              <option value="Mandarin">Mandarin</option>
              <option value="Cantonese">Cantonese</option>
              <option value="Spanish">Spanish</option>
              <option value="Tagalog/Filipino">Tagalog/Filipino</option>
              <option value="Vietnamese">Vietnamese</option>
              <option value="Russian">Russian</option>
              <option value="French">French</option>
              <option value="Korean">Korean</option>
              <option value="Persian">Persian</option>
              <option value="Hindi">Hindi</option>
              <option value="German">German</option>
              <option value="Japanese">Japanese</option>
              <option value="Arabic">Arabic</option>
              <option value="Ilocano">Ilocano</option>
              <option value="Samoan">Samoan</option>
              <option value="Hawaiian or Other Austronesian Languages">
                Hawaiian or Other Austronesian Languages
              </option>
              <option value="Portuguese">Portuguese</option>
              <option value="Italian">Italian</option>
              <option value="Thai">Thai</option>
              <option value="Lao or Other Tai-Kadai Languages">
                Lao or Other Tai-Kadai Languages
              </option>
              <option value="Armenian">Armenian</option>
              <option value="Farsi">Farsi</option>
              <option value="Dari">Dari</option>
              <option value="Hebrew">Hebrew</option>
              <option value="Khmer">Khmer</option>
              <option value="Amharic">Amharic</option>
              <option value="Somali or Other Afro-Asiatic Languages">
                Somali or Other Afro-Asiatic Languages
              </option>
              <option value="Ukrainian">Ukrainian</option>
              <option value="Bengali">Bengali</option>
              <option value="Nepali">Nepali</option>
              <option value="Marathi or Other Indic Languages">
                Marathi or Other Indic Languages
              </option>
              <option value="Tamil">Tamil</option>
              <option value="Urdu">Urdu</option>
              <option value="Serbo-Croatian">Serbo-Croatian</option>
              <option value="Swahili or Other Languages of Central">
                Swahili or Other Languages of Central
              </option>
              <option value="Eastern">Eastern and Southern Africa</option>
              <option value="Gujarati">Gujarati</option>
              <option value="Greek">Greek</option>
              <option value="Yiddish">Yiddish</option>
              <option
                value="Pennsylvania Dutch or Other West Germanic Languages"
              >
                Pennsylvania Dutch or Other West Germanic Languages
              </option>
              <option value="Punjabi">Punjabi</option>
              <option value="Malayalam">Malayalam</option>
              <option value="Kannada">Kannada</option>
              <option value="or Other Dravidian Languages">
                or Other Dravidian Languages
              </option>
              <option value="Telugu">Telugu</option>
              <option value="Polish">Polish</option>
              <option value="Yoruba">Yoruba</option>
              <option value="Twi">Twi</option>
              <option value="Igbo or Other Languages of Western Africa">
                Igbo or Other Languages of Western Africa
              </option>
              <option value="Hmong">Hmong</option>
              <option value="Haitian">Haitian</option>
              <option value="Navajo">Navajo</option>
              <option value="Do not wish to disclose">
                Do not wish to disclose
              </option>
            </select>
          </div>
          <div
            class="error"
            v-if="
              validator.account.language.$error &&
              !validator.account.language.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.customerName.$error,
            }"
          >
            <label class="form__label"
              >Customer Name On Utility Account<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.customerName"
              v-model="validator.account.customerName.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.customerName.$error &&
              !validator.account.customerName.required
            "
          >
            * Required
          </div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.pgeElectricSAID.$error,
            }"
          >
            <label class="form__label"
              >PG&amp;E Electric SAID<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.pgeElectricSAID"
              v-model="validator.account.pgeElectricSAID.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.pgeElectricSAID.$error &&
              !validator.account.pgeElectricSAID.required
            "
          >
            * Required
          </div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.customerEmail.$error,
            }"
          >
            <label class="form__label"
              >Customer Email Address<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.customerEmail"
              v-model="validator.account.customerEmail.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.customerEmail.$error &&
              !validator.account.customerEmail.required
            "
          >
            * Required
          </div>
          <div class="form-group">
            <label class="form__label">Household Gross Annual Income</label>
            <select
              name="account.householdGrossIncome"
              class="form__input"
              v-model="account.householdGrossIncome"
            >
              <option value="" default selected hidden>Select Any</option>
              <option value="Less than $48,000">Less than $48,000</option>
              <option value="$48,000 to $125,000">$48,000 to $125,000</option>
              <option value="Greater than $125,000">
                Greater than $125,000
              </option>
              <option value="Not disclosed">Do not wish to disclose</option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['account', 'validator'],
}
</script>
