<template>
  <div class="container">
    <h1>contact</h1>
    <form @submit.prevent="sendEmail">
      <div class="row justify-content-md-center">
        <div class="col-md-auto">
          <label>name</label>
          <input type="text" v-model="name" name="name" placeholder="your name">
        </div>
      </div>
      <div class="row justify-content-md-center">
        <div class="col-md-auto">
          <label>email</label>
          <input type="email" v-model="email" name="email" placeholder="your email">
        </div>
      </div>
      <div class="row justify-content-md-center">
        <div class="col-md-auto">
          <label>message</label>
          <textarea name="message" v-model="message" cols="30" rows="5" placeholder="message">
          </textarea>
          <input class="customBtnDesign" id="submitBtn" type="submit" value="send">
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  name: 'Contact',
  data() {
    return {
      name: '',
      email: '',
      message: ''
    }
  },
  methods: {
    sendEmail(e) {
      try {
        // TO DO: ADD VARIABLES AS GITHUB KEYS
        emailjs.sendForm('service_u6ie8iz', 'template_9jskeh6', e.target,
          '25pK8EaCBXSYEZdoh', {
          name: this.name,
          email: this.email,
          message: this.message
        })

      } catch (error) {
        console.log({ error })
      }
      // Reset form field
      this.name = ''
      this.email = ''
      this.message = ''
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
label {
  display: block;
  margin: 20px;
}

#submitBtn {
  display: block;
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  color: #42b983;
  opacity: .5;
  background-color: white;
}

#submitBtn:hover{
  opacity: 1;
}
</style>