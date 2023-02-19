<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <form @submit="submitForm" >
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name" />
    </div>
        <div>
      <label for="age">Age</label>
      <input type="number" id="age" v-model.number="formValues.age" />
    </div>
    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" v-model="formValues.profileSummary" />
    </div>

    <div>
      <label for="country">Country</label>
      <select name="country" id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="bulgaria">Bulgaria</option>
        <option value="germany">Germany</option>
        <option value="greece">Greece</option>
      </select>
    </div>

        <div>
      <label for="location">Job Location</label>
      <select  multiple id="location" v-model="formValues.location">
        <option value="bulgaria">Bulgaria</option>
        <option value="germany">Germany</option>
        <option value="greece">Greece</option>
      </select>
    </div>

    <div>
      <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
      <label for="remoteWork">Open to remote work?</label>
    </div>


    <div>
      <label>Skill set</label>
      <input
        type="checkbox"
        id="html"
        value="html"
        v-model="formValues.skillSet"
      />
      <label>HTML</label>
      <input
        type="checkbox"
        id="css"
        value="css"
        v-model="formValues.skillSet"
      />
      <label>CSS</label>
      <input
        type="checkbox"
        id="javascript"
        value="javascript"
        v-model="formValues.skillSet"
      />
      <label>JavaScript</label>
    </div>


    <div>
      <label>Years of Experience</label>
      <input type="radio" value="0-2" v-model="formValues.yearsOfExperience" />
      <label>0-2</label>
      <input type="radio" value="3-5" v-model="formValues.yearsOfExperience" />
      <label>3-5</label>
      <input type="radio" value="6-10" v-model="formValues.yearsOfExperience" />
      <label>5-10</label>
      <input type="radio" value="10+" v-model="formValues.yearsOfExperience" />
      <label>10+</label>
    </div>

    <div><button>Submit</button></div>

  </form>
</template>

<script>
export default {
  name: "FormHandling",
  components: {},
  data() {
    return {
      formValues: {
        name: '',
        profileSummary: '',
        country: '',
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        yearsOfExperience: '',
        age: null,
      },
    };
  },
  methods: {
    submitForm(event){
      event.preventDefault();
      console.log('Form value: ', this.formValues);
    }
  }
};
</script>
<style>
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}</style>
