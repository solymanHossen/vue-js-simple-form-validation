<template>
  <div>
    <div>
      {{ JSON.stringify(formValues) }}
    </div>
    <br />
    <form @submit="submitForm">
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model="formValues.name" />
      </div>
      <br />
      <div>
        <label for="profile"> Profile summary</label>
        <textarea id="profile" v-model="formValues.profileSummary" />
      </div>
      <br />
      <div>
        <label for="country">country</label>
        <select name="" id="country" v-model="formValues.country">
          <option value="">select a country</option>
          <option value="bd">Bangladesh</option>
          <option value="india">India</option>
          <option value="pakistan">Pakistan</option>
        </select>
      </div>
      <br />
      <div>
        <label for="job_location">Job Location</label>
        <select name="" id="country" multiple v-model="formValues.joblocation">
          <option value="">select a country</option>
          <option value="bd">Bangladesh</option>
          <option value="india">India</option>
          <option value="pakistan">Pakistan</option>
        </select>
      </div>
      <br />
      <div>
        <input
          type="checkbox"
          id="remoteWork"
          v-model="formValues.remotoWork"
          true-value="yes"
          false-value="no"
        />
        <label for="remotWork">Open to remote work</label>
      </div>
      <br /><br />
      <div>
        <label for="">Skills:</label>
        <input
          type="checkbox"
          id="html"
          value="html"
          v-model="formValues.skillSet"
        />
        <label for="html">Html</label>
        <input
          type="checkbox"
          id="css"
          value="css"
          v-model="formValues.skillSet"
        />
        <label for="css">css</label>
      </div>
      <br /><br /><br />
      <button type="submit">submit your data</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        joblocation: [],
        remotoWork: "no",
        skillSet: [],
      },
    };
  },
  methods: {
    submitForm(event) {
      event.preventDefault();
      console.log("form values data", this.formValues);
    },
  },
};
</script>

<style>
h2 {
  height: 50px;
  border-radius: 10px;

  background: green;
  text-align: center;
}
</style>
