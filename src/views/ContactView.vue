<template>
    <div id="contact">
      <div class="container">
        <div class="row">
          <div class="contact-left">
            <h1 class="sub-title">Contact Me</h1>
            <p><i class="fa-solid fa-paper-plane"></i> haanimpietersen@gmail.com</p>
            <p><i class="fa-solid fa-phone"></i> 0714332419</p>
            <div class="social-icons">
              <a href="https://www.facebook.com/profile.php?id=100089705331205"><i class="fa-brands fa-facebook animate__animated animate__bounce"></i></a>
              <a href="https://twitter.com/nimmie_13"><i class="fa-brands fa-twitter-square animate__animated animate__bounce"></i></a>
              <a href="https://instagram.com/the.one.and.only.haanim?igshid=MzMyNGUyNmU2YQ=="><i class="fa-brands fa-instagram animate__animated animate__bounce"></i></a>
              <a href="https://za.linkedin.com/in/haanim-pietersen-172bb9264"><i class="fa-brands fa-linkedin animate__animated animate__bounce"></i></a>
            </div>
          </div>
          <div class="contact-right">
          <form v-on:submit.prevent="submitForm" class="contact-form animate__animated animate__zoomInRight">
            <label class="form-label">
              Your Name:
              <input type="text" v-model="formData.name" class="form-input" :class="{ 'error': !formData.name && submitted }">
              <span v-if="!formData.name && submitted" class="error-message">Please fill out this field</span>
            </label>
            <label class="form-label">
              Your Email:
              <input type="email" v-model="formData.email" class="form-input" :class="{ 'error': !formData.email && submitted }">
              <span v-if="!formData.email && submitted" class="error-message">Please fill out this field</span>
            </label>
            <label class="form-label">
              Your Message:
              <textarea rows="6" v-model="formData.message" class="form-textarea"></textarea>
            </label>
            <button type="submit" class="btn btn-submit">Submit</button><br><br>
            <span v-if="submitted && (!formData.name || !formData.email)" class="error-message">Please fill out all required fields</span>
          </form>
        </div>
      </div>
    </div>
    <MapComponent />
  </div>
</template>

<script>
import 'animate.css';
import MapComponent from '../components/MapComponent.vue';
export default {
  components: {
    MapComponent
  },
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      },
      submitted: false // Added to track if the form has been submitted
    };
  },
  methods: {
    submitForm() {
      this.submitted = true; // Set submitted to true when the form is submitted

      // Validate the form
      if (!this.formData.name || !this.formData.email) {
        console.log('Please fill out all required fields');
        return;
      }

      // Handle form submission logic here
      console.log('Form submitted!', this.formData);
      // You can add additional logic, such as sending a request to your server or using Formspree
    }
  }
};
</script>
  
  <style scoped>
  #contact {
    background-color: #664229;
    padding: 50px 0;
    color: #D2B48C;
  }
  
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .row {
    display: flex;
    justify-content: space-between;
  }
  
  .contact-left {
    width: 45%;
  }
  
  .sub-title {
    font-size: 24px;
    margin-bottom: 20px;
  }
  
  .social-icons {
    margin-top: 20px;
  }
  
  .social-icons a {
    color: #D2B48C;
    font-size: 24px;
    margin-right: 10px;
    display: inline-block;
    margin: 0 0.5rem;
    animation: bounce var(--animate-duration) infinite;;
  }

  @keyframes bounce {
    0%, 20%, 50%, 80%, 100% {
      transform: translateY(0);
    }
    40% {
      transform: translateY(-30px);
    }
    60% {
      transform: translateY(-15px);
    }
  }
  
  .contact-right {
    width: 45%;
  }
  
  .contact-form {
    background-color: #987554;
    padding: 20px;
    border-radius: 8px;
  }
  
  .form-label {
    display: block;
    margin-bottom: 10px;
  }
  
  .form-input,
  .form-textarea {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border: 1px solid #D2B48C;
    border-radius: 4px;
    background-color: #fff;
    color: #2c3e50;
  }

  
  .btn-submit {
    background-color: #664229;
  }
  
  .error-message {
  color: #e74c3c;
  font-size: 14px;
  font-weight: 600;
  margin-top: 5px;
}

/* Add this style to highlight fields with errors */
.error {
  border-color: #e74c3c;
}

.my-element {
  display: inline-block;
  margin: 0 0.5rem;

  animation: bounce; /* referring directly to the animation's @keyframe declaration */
  animation-duration: 2s; /* don't forget to set a duration! */
}

@media (max-width: 768px) {
    .row {
      flex-direction: column; /* Change flex direction to column for stacking both contact sections */
    }

    .contact-left,
    .contact-right {
      width: 100%; 
    }

    .contact-right {
      margin-top: 40px;
    }
  }

  </style>