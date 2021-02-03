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
                        <div class="formItem">
                            <input type="text" />
                            <span class="inputLabel">Full Name*</span>
                            <span class="inputRequired">The field is required</span>
                        </div>
                        <div class="formItem">
                            <input type="text" />
                            <span class="inputLabel">E-mail*</span>
                            <span class="inputRequired">The field is required</span>
                        </div>
                        <div class="formItem">
                            <input type="text" />
                            <span class="inputLabel">Phone*</span>
                            <span class="inputRequired">The field is required</span>
                        </div>
                        <div class="formItem dropdownSelectionWrapper">
                            <div class="category">
                                <select>
                                    <option disabled selected>Category</option>
                                </select>
                            </div>
                            <div class="subcategory">
                                <select>
                                    <option disabled selected>Subcategory</option>
                                </select>
                            </div>
                        </div>
                        <div class="formItem">
                            <textarea></textarea>
                            <span class="inputLabel">Message</span>
                        </div>
                        <div class="checkboxSelectionsWrapper">
                            <div class="checkboxSelectionsTitle">
                                Please select at least one of the following:
                            </div>
                            <div class="checkboxSelections">
                                <div class="generalCheckbox">
                                    <input id="option1" type="checkbox" value="option1"/>
                                    <label for="option1">Option 1</label>
                                </div>
                                <div class="generalCheckbox">
                                    <input id="option2" type="checkbox" value="option2"/>
                                    <label for="option2">Option 2</label>
                                </div>
                            </div>
                        </div>
                        <div class="submitButtonWrapper">
                            <div class="generalButton lg">
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
    export default {
        name: "Contact"
    }
</script>

<style scoped>

</style>
