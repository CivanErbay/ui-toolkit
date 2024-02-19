<template>
  <v-container>
    <v-row class="pt-12" justify="center">
      <v-col cols="12" sm="6">
        <v-form ref="form" v-model="valid">
          <v-text-field v-model="name" label="Name" :rules="[rules.required]" required></v-text-field>
          <v-text-field v-model="email" label="Email" :rules="[rules.required, rules.email]" required></v-text-field>
          <v-select v-model="gender" :items="genders" label="Gender" required></v-select>
          <v-checkbox v-model="subscribe" label="Subscribe to newsletter"></v-checkbox>
          <v-autocomplete v-model="country" :items="countries" label="Country" required></v-autocomplete>
          <v-slider v-model="age" label="Age" thumb-label></v-slider>
          <v-radio-group v-model="paymentMethod" row>
            <v-radio label="Credit Card" value="credit"></v-radio>
            <v-radio label="PayPal" value="paypal"></v-radio>
          </v-radio-group>
          <v-textarea v-model="message" label="Message"></v-textarea>
          <v-date-picker v-model="date" label="Date" required></v-date-picker>
          <v-time-picker v-model="time" label="Time" required></v-time-picker>
          <v-file-input label="File" prepend-icon="mdi-paperclip" v-model="file" accept="image/*"></v-file-input>
          <v-btn color="primary" @click="submitForm">Submit</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { ref } from 'vue';
export default {
  name: 'VuetifyComponentShowcase',
  data() {
    return {
      valid: false,
      name: '',
      email: '',
      gender: null,
      genders: ['Male', 'Female', 'Other'],
      subscribe: false,
      country: null,
      countries: ['USA', 'Canada', 'UK', 'Germany', 'France'],
      age: 18,
      paymentMethod: null,
      message: '',
      date: null,
      time: null,
      file: null,
      rules: {
        required: value => !!value || 'This field is required.',
        email: value => {
          const pattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
          return pattern.test(value) || 'Invalid email.';
        }
      }
    };
  },
  methods: {
    submitForm() {
      if (this.$refs.form.validate()) {
        // Form is valid, perform submit action here
        console.log('Form submitted successfully');
      }
    }
  }
}
</script>

<style>
/* Add custom styles here */
</style>
