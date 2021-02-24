<template>
  <div :class="[displayGridAll]">
    <!-- <HelloWorld :msg="message" /> -->
    <div>
      <h1>We'll like to hear from you!</h1>
    </div>
    <div :class="[displayGridSub]">
      <div><img alt="Vue logo" src="../assets/logo.png" /></div>
      <br />
      <div>
        <form action="">
          <label for="">Firstname: </label>
          <input v-model="firstName" type="text" placeholder="Firstname" />
          <br />
          <br />
          <label for="">Email Address: </label>
          <input v-model="email" type="text" placeholder="email@example.com" />
          <br />
          <br />
          <label for="">Drop us a message:</label>
          <textarea
            v-model="message"
            name=""
            id=""
            cols="30"
            rows="10"
            placeholder="Drop us a message"
          ></textarea>
          <br />
          <br />
          <button @click="onClick" :disabled="isTextareaInvalid" type="submit">
            Submit
          </button>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "contactForm",
  //   props: {
  //     details: {
  //       required: true,
  //       type: Object,
  //     },
  //   },
  data() {
    return {
      allFormDetails: [],
      firstName: "",
      email: "",
      message: "",
      displayGridAll: "container",
      displayGridSub: "form-div",
      isDisabled: true,
    };
  },
  methods: {
    onClick() {
    //   allFormDetails.push(formDetails);
      alert("Congrats " + this.firstName + ". Your message has been received.");
      //   this.$emit("details", {});
      this.firstName = "";
      this.email = "";
      this.message = "";
      this.isDisabled = true;
    },
  },
  computed: {
    isTextareaInvalid() {
      if (this.message.length < 2) {
        return true;
      }
      return false;
    },
  },
};
</script>

<style scoped>
.container {
  display: grid;
  grid-template-rows: 0.1fr 1fr;
  justify-content: center;
  align-content: center;
  align-items: center;
}
.form-div {
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  background-color: #41b883;
  margin-top: 10px;
}
form {
  padding: 40px;
}
form > label {
  text-align: left;
  font-size: 14px;
  font-weight: bold;
  display: block;
  margin-bottom: 5px;
}
form > input,
form > button {
  text-align: left;
  height: 30px;
  width: 100%;
  border-radius: 10px;
  border: 2px solid #35495e;
  outline: #35495e;
  color: #35495e;
  /* padding: 3px; */
}
form > textarea {
  border: 2px solid #35495e;
  width: 100%;
  outline: #35495e;
  /* padding: 3px; */
  color: #35495e;
}
form > button {
  text-align: center;
  background-color: #35495e;
  color: #41b883;
  font-weight: bold;
  font-size: 15px;
}
</style>