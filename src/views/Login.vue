<template>
  <form class="login-page" @submit.prevent="submitForm()">

    <div class="text-input">
      <input type="text"
        v-model.trim="emailValue"
        class="text-input__field"
        :class="{
          '_invalid': emailCorrect === false,
          '_valid': emailCorrect
        }"  
        onfocus="this.nextElementSibling.classList.remove('_unvisited')"
        @input="verifyEmail()"
        @blur="verifyEmail()" >

      <p class="text-input__placeholder _unvisited">
        E-mail
      </p>

      <p v-show="emailCorrect === false" class="text-input__warning">
        Неверный email
      </p>
    </div>



    <div class="text-input">
      <input type="text"
        v-model.trim="passwordValue"
        class="text-input__field"
        :class="{
          '_invalid': passwordCorrect === false,
          '_valid': passwordCorrect
        }"
        onfocus="this.nextElementSibling.classList.remove('_unvisited')"
        @input="verifyPassword()"
        @blur="verifyPassword()">

      <p class="text-input__placeholder _unvisited">
        Пароль
      </p>

      <p v-show="passwordCorrect === false" class="text-input__warning">
        Неверный пароль
      </p>
    </div>



    <button class="login-submit-btn" :disabled="(emailCorrect && passwordCorrect) ? false : true">
      войти
    </button> 

    <Loader v-show="pending" />
  </form>
</template>



<script>
import Loader from '@/components/Loader.vue'

export default {
  components: { Loader },

  data () {
    return {
      emailValue: '',
      emailCorrect: undefined,      
      passwordValue: '',
      passwordCorrect: undefined,
      pending: false
    }
  },


  methods: {
    verifyEmail () {
      this.emailCorrect = /^\w+@\w+\.\w+$/.test(this.emailValue)
    },

    verifyPassword () {
      this.passwordCorrect = /^\w{8,}$/.test(this.passwordValue) && /[A-Z]/.test(this.passwordValue)
    },

    submitForm () {
      this.pending = true;
      setTimeout(() => this.$router.push('/'), 2000)
    }
  }
}
</script>



<style>
.login-page {
  position: relative;
  max-width: 400px;
  margin: 0 auto;
}

.text-input {
  min-height: 56px;
  position: relative;
  padding-top: 16px;
  margin-top: 30px;
}
.text-input:first-of-type {
  margin-top: 0;
}



.text-input__field {
  width: 100%;
  height: 40px;
  padding: 2px 12px 0;
  border-bottom: 1px solid gray;
}
._invalid {
  border-bottom-color: tomato;
}
._valid {
  border-bottom-color: dodgerblue;
}



.text-input__placeholder {
  line-height: 16px;
  font-size: 0.9rem;
  position: absolute;
  z-index: -1;
  left: 5px;
  top: 0;
  transition: 0.4s;
}

._unvisited {
  font-size: 1rem;
  left: 12px;
  top: 27px;
}

.text-input__warning {
  line-height: 16px;
  font-size: 0.8rem;
  margin-top: 8px;
  padding-left: 5px;
  color: tomato;
}



.login-submit-btn {
  background: dodgerblue;
  border-radius: 8px;
  color: white;
  font-size: 1.25rem;
  width: 100%;
  height: 42px;
  margin-top: 56px;
}

.login-submit-btn:disabled {
  background: whitesmoke;
  color: lightgray;
}

</style>
