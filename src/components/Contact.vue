<template>
    <div class="contactInner">
        <div class="mapWrapper">
            <img src="/assets/map/map.jpg" />
        </div>
        <div class="contactFormWrapper">
            <div class="contactFormInner">
                <div class="generalTitle">
                    Contact us
                </div>
                <div class="generalText">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </div>
                <div class="contactForm">
                    <form>
                        <div class="formItem" :class="{hasError: form.name.hasError.value}">
                            <input id="nameInput" v-model="form.name.value"  type="text" @keyup="validateInput(form.name)" @focus="activeInputLabel(form.name)" @blur="disableInputLabel(form.name)" />
                            <span class="inputLabel" :class="{active: form.name.inputLabel.active }">{{form.name.inputLabel.value}}</span>
                            <span v-if="form.name.isRequired && !form.name.hasError.value && !form.name.successState" class="inputRequired">{{form.name.inputRequired.warningText}}</span>
                            <span v-if="form.name.hasError.value" class="inputRequired">{{form.name.inputRequired.validationText}}</span>
                            <span v-if="form.name.successState" class="inputRequired">{{form.name.inputRequired.successText}}</span>
                            <span v-if="form.name.successState" class="successTick"><img src="/assets/general/successTick.png"/></span>
                        </div>
                        <div class="formItem" :class="{hasError: form.email.hasError.value}">
                            <input id="emailInput" v-model="form.email.value" type="text"  @keyup="validateInput(form.email)" @focus="activeInputLabel(form.email)" @blur="disableInputLabel(form.email)" />
                            <span class="inputLabel" :class="{active: form.email.inputLabel.active}">{{form.email.inputLabel.value}}</span>
                            <span v-if="form.email.isRequired && !form.email.hasError.value && !form.email.successState" class="inputRequired">{{form.email.inputRequired.warningText}}</span>
                            <span v-if="form.email.hasError.value" class="inputRequired">{{form.email.inputRequired.validationText}}</span>
                            <span v-if="form.email.successState" class="inputRequired">{{form.email.inputRequired.successText}}</span>
                            <span v-if="form.email.successState" class="successTick"><img src="/assets/general/successTick.png"/></span>
                        </div>
                        <div class="formItem" :class="{hasError: form.phone.hasError.value}">
                            <input id="phoneInput" v-model="form.phone.value" type="text"  @keyup="validateInput(form.phone)" @focus="activeInputLabel(form.phone)" @blur="disableInputLabel(form.phone)" />
                            <span class="inputLabel" :class="{active: form.phone.inputLabel.active }">{{form.phone.inputLabel.value}}</span>
                            <span v-if="form.phone.isRequired && !form.phone.hasError.value && !form.phone.successState" class="inputRequired">{{form.phone.inputRequired.warningText}}</span>
                            <span v-if="form.phone.hasError.value" class="inputRequired">{{form.phone.inputRequired.validationText}}</span>
                            <span v-if="form.phone.successState" class="inputRequired">{{form.phone.inputRequired.successText}}</span>
                            <span v-if="form.email.successState" class="successTick"><img src="/assets/general/successTick.png"/></span>
                        </div>
                        <div class="formItem dropdownSelectionWrapper">
                            <div class="category">
                                <select v-model="form.categories.selected" @change="setSubcategories">
                                    <option disabled selected>Category</option>
                                    <option v-for="category in form.categories.data" :key="category.categoryId" :value="category">{{category.name}}</option>

                                </select>
                            </div>
                            <div class="subcategory">
                                <select v-model="form.subcategories.selected">
                                    <option disabled selected>Subcategory</option>
                                    <option v-for="subcategory in form.subcategories.data" :key="subcategory.categoryId" :value="subcategory">{{subcategory.name}}</option>
                                </select>
                            </div>
                        </div>
                        <div class="formItem" :class="{hasError: form.message.hasError.value}">
                            <textarea  v-model="form.message.value"
                                       :maxlength="form.message.charsMaxLength"
                                       @keyup="validateInput(form.message)"
                                       @focus="activeInputLabel(form.message)"
                                       @blur="disableInputLabel(form.message)" ></textarea>
                            <span class="inputLabel" :class="{active: form.message.inputLabel.active }">Message</span>
                            <span v-if="form.message.isRequired" class="inputRequired">{{form.message.inputRequired.warningText}}</span>
                            <span v-if="form.message.hasError.value" class="inputRequired">{{form.message.inputRequired.validationText}}</span>
                            <div class="messageCounter">
                                {{form.message.value.length}} / {{form.message.charsMaxLength}}
                            </div>
                        </div>
                        <div class="checkboxSelectionsWrapper">
                            <div class="checkboxSelectionsTitle">
                                Please select at least one of the following:
                                <span v-if="form.checkOptions.hasError.value" class="checkboxError">{{form.checkOptions.inputRequired.validationText}}</span>
                            </div>

                            <div class="checkboxSelections">
                                <div class="generalCheckbox">
                                    <input v-model="form.checkOptions.selections" @change="validateInput(form.checkOptions)" id="option1" type="checkbox" value="option1"/>
                                    <label for="option1">Option 1</label>
                                </div>
                                <div class="generalCheckbox">
                                    <input v-model="form.checkOptions.selections" @change="validateInput(form.checkOptions)" id="option2" type="checkbox" value="option2"/>
                                    <label for="option2">Option 2</label>
                                </div>
                            </div>
                        </div>
                        <div class="submitButtonWrapper">
                            <div class="generalButton lg" :class="{disable: formHasErrors === null || formHasErrors}">
                                Submit
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: "Contact",
        data() {
          return {
              form: {
                  name: {
                      id:'name',
                      regex: /^[a-zA-Z\s]*$/g, // match only letters
                      value: '',
                      inputRequired: {
                          warningText: 'The field is required',
                          successText: 'Success Text',
                          validationText: 'Cannot be empty and only letters required'
                      },
                      inputLabel: {
                          value: 'Full Name*',
                          active: false
                      },
                      isRequired: true,
                      hasError: {
                          value: null,
                          message: 'Only letters required'
                      },
                      successState: null
                  },
                  email: {
                      id:'email',
                      regex: /^[A-Za-z0-9._%+-]+@spitogatos.gr*$/g,
                      value: '',
                      inputRequired: {
                          warningText: 'The field is required',
                          successText: 'Success Text',
                          validationText: 'A valid email address required with @spitogatos.gr suffix'
                      },
                      inputLabel: {
                          value: 'Email*',
                          active: false
                      },
                      isRequired: true,
                      hasError: {
                          value: null
                      },
                      successState: null
                  },
                  phone: {
                      id:'phone',
                      regex: /^[0-9]{10}$/g,
                      value: '',
                      inputRequired: {
                          warningText: 'The field is required',
                          successText: 'Success Text',
                          validationText: 'Cannot be empty and only 10 numbers required'
                      },
                      inputLabel: {
                          value: 'Phone*',
                          active: false
                      },
                      isRequired: true,
                      hasError: {
                          value: null
                      },
                      successState: null
                  },
                  categories: {
                      selected:'Category',
                      data:[]
                  },
                  subcategories: {
                      selected:'Subcategory',
                      data:[]
                  },
                  message: {
                      id:'message',
                      regex: /^(.*?)$/g,
                      value: '',
                      inputRequired: {
                          warningText: 'The field is required',
                          successText: 'Success Text',
                          validationText: ''
                      },
                      inputLabel: {
                          value: 'Message',
                          active: false
                      },
                      isRequired: false,
                      hasError: {
                          value: null
                      },
                      successState: null,
                      charsMaxLength: 100
                  },
                  checkOptions: {
                      id:'checkboxes',
                      inputRequired: {
                          warningText: 'The field is required',
                          successText: 'Success Text',
                          validationText: 'You must choose at least one option'
                      },
                      selections:[],
                      hasError:{
                          value: null
                      }
                  }
              }
          }
        },
        computed:{
            formHasErrors: function () {
                return this.form.name.hasError.value || this.form.email.hasError.value || this.form.phone.hasError.value || this.form.checkOptions.hasError.value
            }
        },
        methods: {
            async fetchDropdownData(){
                const response = await axios.get('https://run.mocky.io/v3/0b8fbded-6ce4-4cb2-bf2f-d2c39207506b')
                const result = await response.data
                this.form.categories.data = result
            },
            setSubcategories() {
                this.form.subcategories.selected = 'Subcategory'
                if(this.form.categories.selected.name === 'All'){
                    const allSubCategories = []
                    this.form.categories.data.forEach(cat => {
                        if(cat.subCategories){
                            cat.subCategories.forEach(sub=> {
                                allSubCategories.push(sub)
                            })
                        }
                    })
                    this.form.subcategories.data = allSubCategories
                }
                if(this.form.categories.selected.subCategories===undefined && this.form.categories.selected.name !== 'All' ){
                    this.form.subcategories.data = []
                }
                if(this.form.categories.selected.subCategories) {
                    this.form.subcategories.data = this.form.categories.selected.subCategories
                }
            },
            validateInput(formInput) {
                if(formInput.id === 'checkboxes'){
                    if(formInput.selections.length === 0) {
                        formInput.hasError.value = true
                    }else {
                        formInput.hasError.value = false
                    }
                }else {
                    if(formInput.regex.test(formInput.value) && formInput.value.length > 0){
                        formInput.hasError.value = false
                        formInput.successState = true
                    } else{
                        formInput.hasError.value = true
                        formInput.successState = false
                    }
                    formInput.regex.test(formInput.value)
                }
            },
            activeInputLabel(formInput){
                formInput.inputLabel.active = true
            },
            disableInputLabel(formInput) {
                if(formInput.value.length===0) {
                    formInput.inputLabel.active = false
                }
            }
        },
        async mounted() {
            await this.fetchDropdownData()
        }
    }
</script>

<style scoped>

</style>
