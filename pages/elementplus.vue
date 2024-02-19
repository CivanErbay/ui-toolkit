<template>
  <div class="container">
    <el-container>
      <el-main>
        <el-form
          :model="form"
          :rules="rules"
          ref="form"
          label-width="120px"
          size="large"
        >
          <el-form-item label="Name" prop="name">
            <el-input v-model="form.name"></el-input>
          </el-form-item>
          <el-form-item label="Email" prop="email">
            <el-input v-model="form.email"></el-input>
          </el-form-item>
          <el-form-item label="Gender" prop="gender">
            <el-select
              v-model="form.gender"
              placeholder="Select Gender"
            >
              <el-option label="Male" value="male"></el-option>
              <el-option label="Female" value="female"></el-option>
              <el-option label="Other" value="other"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item>
            <el-checkbox
              v-model="form.subscribe"
              label="Subscribe to newsletter"
            ></el-checkbox
            ><el-checkbox
              v-model="form.subscribe"
              border
              label="Subscribe to newsletter"
            ></el-checkbox>
          </el-form-item>
          <el-form-item label="Country" prop="country">
            <el-autocomplete
              v-model="form.country"
              :fetch-suggestions="querySearch"
              placeholder="Type to search"
            ></el-autocomplete>
          </el-form-item>
          <el-form-item label="Age" prop="age">
            <el-slider v-model="form.age"></el-slider>
          </el-form-item>
          <el-form-item prop="paymentMethod">
            <el-radio-group v-model="form.paymentMethod">
              <el-radio label="Credit Card"></el-radio>
              <el-radio label="PayPal"></el-radio>
            </el-radio-group>
          </el-form-item>
          <el-form-item label="Message" prop="message">
            <el-input
              type="textarea"
              v-model="form.message"
            ></el-input>
          </el-form-item>
          <el-form-item label="Date" prop="date">
            <el-date-picker
              v-model="form.date"
              type="date"
            ></el-date-picker>
          </el-form-item>
          <el-form-item label="Time" prop="time">
            <el-time-picker v-model="form.time"></el-time-picker>
          </el-form-item>
          <el-form-item label="File" prop="file">
            <el-upload
              class="upload-demo"
              action="https://jsonplaceholder.typicode.com/posts/"
              :show-file-list="false"
              :on-success="handleSuccess"
            >
              <el-button size="small" type="primary"
                >Click to upload</el-button
              >
            </el-upload>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="submitForm"
              >Submit</el-button
            >
          </el-form-item>
        </el-form>
      </el-main>
    </el-container>
  </div>
</template>

<script>
export default {
  name: 'ElementPlusComponentShowcase',
  data() {
    return {
      form: {
        name: '',
        email: '',
        gender: '',
        subscribe: false,
        country: '',
        age: 18,
        paymentMethod: '',
        message: '',
        date: '',
        time: '',
        file: ''
      },
      rules: {
        name: [{ required: true, message: 'Please input name', trigger: 'blur' }],
        email: [{ required: true, message: 'Please input email', trigger: 'blur' }],
        gender: [{ required: true, message: 'Please select gender', trigger: 'change' }],
        country: [{ required: true, message: 'Please select country', trigger: 'change' }],
        age: [{ required: true, message: 'Please select age', trigger: 'change' }],
        paymentMethod: [{ required: true, message: 'Please select payment method', trigger: 'change' }],
        message: [{ required: true, message: 'Please input message', trigger: 'blur' }],
        date: [{ required: true, message: 'Please select date', trigger: 'change' }],
        time: [{ required: true, message: 'Please select time', trigger: 'change' }],
        file: [{ required: true, message: 'Please upload file', trigger: 'change' }]
      }
    };
  },
  methods: {
    submitForm() {
      this.$refs.form.validate((valid) => {
        if (valid) {
          console.log('Form submitted successfully');
        } else {
          console.log('Form validation failed');
          return false;
        }
      });
    },
    handleSuccess(response, file, fileList) {
      console.log('Upload success:', response);
    },
    querySearch(queryString, cb) {
      const countries = ['USA', 'Canada', 'UK', 'Germany', 'France'];
      const results = queryString ? countries.filter(this.createFilter(queryString)) : countries;
      cb(results);
    },
    createFilter(queryString) {
      return (country) => {
        return country.toLowerCase().indexOf(queryString.toLowerCase()) !== -1;
      };
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 800px;
  margin: 30px auto 0;
}
</style>
