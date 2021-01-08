<template>
    <div class="w-2/6 absolute right-0 slide-in top-0 bg-white  text-gray-700 py-10 font-create-round" ref="form" id="form">
        <div id="links" class="mb-11">
            <nav class="w-1/2 float-right text-lg">
                <ul>
                    <li class="inline-block m-2"><a href="#" class=" hover:underline" @click="toggleForm"> {{signin ? 'Sign Up' : 'Sign in'}}</a></li>
                    <li class="inline-block m-2"><a href="#" class=" hover:underline">Download</a></li>
                </ul>
            </nav>

            <div class="w-1/2 h-18"></div>
        </div>

        <div id="form-holder" class="w-full  overflow-y-scroll h-30 px-10">

            <div id="signup-form" class="mt-12" v-if="signup">
                <h1 class="text-2xl font-semibold">Sign up</h1>
                <small>or <a href="#" class="text-blue-700 hover:underline" @click="toggleForm">signin into your account</a></small>

                <div id="form-inputs" class="mt-10 w-full">
                    <input type="text"  class="w-full h-30 border p-2.5 mb-5" placeholder="First name">
                    <input type="text" class="w-full h-30 border p-2.5 mb-5" placeholder="Last name">
                    <input type="text" class="w-full h-30 border p-2.5 mb-5" placeholder="Email">
                    <input type="password" class="w-full h-30 border p-2.5 mb-5" placeholder="Password">

                    <div class="flex mb-3">
                        <input type="checkbox" class="mr-2 relative top-1 rounded-none cursor-pointer w-5 h-5">
                        <span class="mb-3"> I agree to <a href="#" class="text-blue-600 hover:underline">Dropbox Terms</a></span>
                    </div>

                    <button class="w-full bg-blue-600 text-white py-2 px-1.5 mb-3">Sign up</button>

                    <button class="w-full text-black border p-2.5 mb-5 "> <img src="../../public/google.png" class="inline-block" width="20" height="20"> Sign up with Google</button>
                </div>

            </div>

             <div id="signin-form" class="mt-12" v-if="signin">
                <h1 class="text-2xl font-semibold">Sign in</h1>
                <small>or <a href="#" class="text-blue-700 hover:underline" @click="toggleForm">create an account</a></small>

                <div id="form-inputs" class="mt-10 w-full">

                    <input type="text" class="w-full h-30 border p-2.5 mb-5" placeholder="Email">
                    <input type="password" class="w-full h-30 border p-2.5 mb-5" placeholder="Password">

                    <div class="flex mb-1">
                        <input type="checkbox" class="mr-2 relative top-1 rounded-none cursor-pointer w-5 h-5">
                        <span class="mb-4"> Remember me</span>
                    </div>

                    <div class="mb-4">
                        <a href="#" class="text-blue-600 text-sm hover:underline">Forgot your password ?</a>
                    </div>

                    <button class="w-full bg-blue-600 text-white py-2.5 px-1.5 mb-4">Sign in</button>

                    <button class="w-full text-black border p-2.5 mb-4 "> <img src="../../public/google.png" class="inline-block" width="20" height="20"> Sign up with Google</button>

                    <button class="w-full text-black border p-2.5 mb-4 "> <img src="../../public/apple.png" class="inline-block" width="20" height="20"> Sign up with Apple</button>
                </div>

            </div>
        </div>

    </div>
</template>
<script>
export default {
  data () {
    return {
      signin: false,
      signup: true,
      formVissible: true
    }
  },

  mounted () {
    window.addEventListener('scroll', this.animateForm)
  },

  methods: {

    toggleForm () {
      this.signin = !this.signin
      this.signup = !this.signup
    },

    animateForm (event) {
      const form = document.querySelector('#form')
      if (window.pageYOffset > 450) {
        form.classList.remove('slide-in')
        form.classList.add('slide-out')
        this.formVissible = false
      }

      if (window.pageYOffset < 480) {
        if (!this.formVissible) {
          form.classList.remove('slide-out')
          form.classList.add('slide-in')
        }
      }
    }
  }
}
</script>

<style scoped>
    .slide-in {
        width: 33.333%;
        display :block;
        transition: all .20s ease-in;
    }

    .slide-out {
        width: 0;
        display: none;
        transition: all .10s linear;
    }
</style>
