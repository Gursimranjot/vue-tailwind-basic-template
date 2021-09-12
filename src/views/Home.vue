<template>
  <div class="home">
    <div class="w-full">
      <div id="result"></div>
      <form
        id="formField"
        @submit.prevent="formSubmit"
        novalidate
        class="bg-white mb-4 pb-8 pt-6 px-8 rounded shadow-md max-w-xs mx-auto"
      >
        <div class="mb-4">
          <label
            class="block text-gray-700 text-sm font-bold mb-2"
            for="fullname"
          >
            fullname
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="fullname"
            type="text"
            v-model="formData.firstName"
            placeholder="fullname"
          />
          <!-- <h2>Hi {{ formData.firstName }}</h2> -->
        </div>
        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="Email">
            Email
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="Email"
            type="email"
            placeholder="Email"
            v-model="formData.email"
          />
        </div>
        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="DOB">
            Date of birth
          </label>
          <datepicker
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            placeholder="Select Date"
            v-model="formData.date"
          ></datepicker>
        </div>
        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="Email">
            Gender
          </label>
          <div class="mt-2">
            <label class="inline-flex items-center">
              <input
                type="radio"
                class="form-radio"
                name="accountType"
                value="male"
                v-model="formData.Gender"
              />
              <!-- <input @change="change(data)"  v-model="status" type="radio" :value="data.value">
				{{data.label}} -->
              <span class="ml-2">Male</span>
            </label>
            <label class="inline-flex items-center ml-6">
              <input
                type="radio"
                class="form-radio"
                name="accountType"
                value="Female"
                v-model="formData.Gender"
              />
              <span class="ml-2">Female</span>
            </label>
          </div>
        </div>
        <div class="mb-4">
          <label
            class="block text-gray-700 text-sm font-bold mb-2"
            for="country"
          >
            Country
          </label>
          <div class="mt-2">
            <select
              class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
              v-model="formData.country"
            >
              <option>India</option>
              <option>Netherland</option>
              <option>Russia</option>
              <option>Germany</option>
            </select>
          </div>
        </div>

        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="Age">
            Age
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="Age"
            type="text"
            placeholder="Age"
            v-model="formData.Age"
          />
        </div>
        <div class="mb-6">
          <label
            class="block text-gray-700 text-sm font-bold mb-2"
            for="password"
          >
            Password
          </label>
          <!-- border-red-500 -->
          <input
            class="shadow appearance-none border  rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
            id="password"
            type="password"
            placeholder="****"
            v-model="formData.password"
          />
          <p class=" text-xs">Please choose a password.</p>
        </div>
        <div class="flex items-center justify-between">
          <button
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
            type="submit"
          >
            Submit
          </button>
          <!-- <a
            class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800"
            href="#"
          >
            Forgot Password?
          </a> -->
        </div>
      </form>
      <p class="text-center text-gray-500 text-xs">
        &copy; Smartshore Ability. All rights reserved.
      </p>
    </div>
    <div class="formArry">
      <pre>{{ formDatacollection }}</pre>
    </div>
  </div>
</template>

<script>
import Datepicker from "vuejs-datepicker";
export default {
  data() {
    return {
      counter: 0,
      name: "",
      counting: 0,
      number: 0,
      formData: {
        firstName: null,
        email: null,
        date: null,
        Gender: null,
        country: null,
        Age: null,
        password: null,
      },
      submitted: false,
      formDatacollection: localStorage.getItem("userData")
        ? JSON.parse(localStorage.getItem("userData"))
        : [],
    };
  },
  name: "Home",
  components: {
    Datepicker,
  },
  methods: {
    formSubmit() {
      this.formDatacollection.push(this.formData);
      console.log(this.formDatacollection);
      this.formData = {
        firstName: null,
        email: null,
        date: null,
        Gender: null,
        country: null,
        Age: null,
        password: null,
      };
      localStorage.setItem("userData", JSON.stringify(this.formDatacollection));
      alert("Data Processing");
    },
  },
};
</script>
