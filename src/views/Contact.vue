<template>
  <section>
    <div class="container">
      <div class="row">
        <div class="col">
          <form class="contact-form" ref="contactForm" @submit.prevent="submit" method="post">
            <div class="error-message">
              <p class="message-error" v-show="!email.valid">Please enter a valid email address.</p>
              <p
                class="message-error"
                v-show="!message.valid"
              >Message must be at least 30 characters long.</p>
            </div>

            <fieldset>
              <legend>Contact Form</legend>
              <div class="mt-3">
                <label class="label" for="email">Email</label>
                <input
                  type="email"
                  name="email"
                  id="email"
                  placeholder="Your email"
                  required
                  :class="{ email , invalid: !email.valid }"
                  v-model="email.value"
                />
              </div>
              <div class="mt-3">
                <label class="label" for="textarea">Message</label>
                <textarea
                  class="message"
                  name="textarea"
                  type="textarea"
                  id="textarea"
                  placeholder="Your message..."
                  required
                  :class="{ email , invalid: !message.valid }"
                  v-model="message.value"
                  :minlength="message.minlength"
                  ref="message"
                ></textarea>
                <div class="counter">{{ message.value.length }} / {{ message.minlength }}</div>
              </div>
              <div class="mt-3">
                <input type="submit" value="Submit" :disabled="!email.valid && !message.valid" />
              </div>
            </fieldset>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      emailRegExp: /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/,
      email: {
        value: "",
        valid: true
      },
      message: {
        value: "",
        minlength: 30,
        valid: true
      }
    };
  },
  methods: {
    submit() {
      if (this.email.valid && this.message.valid) {
        alert("You have successfully submited the form!");
      } else {
        alert("Please fill out the form as needed!");
      }
    },
    validate(type, value) {
      if (type === "email") {
        this.email.valid = this.emailRegExp.test(value) ? true : false;
      }
      if (type === "message") {
        this.message.valid =
          this.message.value.length >= this.message.minlength ? true : false;
      }
    }
  },
  watch: {
    "email.value"(value) {
      this.validate("email", value);
    },
    "message.value"(value) {
      this.validate("message", value);
    }
  }
};
</script>

<style lang="scss">

label {
  display: block;
}

.message-error {
  color: red;
}

.invalid {
  border: 1px solid red;
}
</style>