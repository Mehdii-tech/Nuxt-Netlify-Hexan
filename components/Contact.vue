<template>
    <form 
  name="contactus" 
  action="/" 
  method="post" 
  netlify
  netlify-honeypot="bot-field"
>
<div class="flex space-x-4 justify-end ">
  <input type="hidden" name="form-name" value="contactus" />
  <div>  
    <input class="h-8 w-96 rounded-full border-2 border-pink-500 px-3 focus:outline-none" type="text" placeholder="MAIL" name="name" required/>
  </div>
  <button class="bg-pink-500 font-semibold text-white hover:bg-pink-400 h-8 w-32 rounded-full" type="submit" value="Send message">Send</button>
</div>
</form>
</template>

<script>
import Button from './Button.vue'
export default {
  components: { Button },
    setup() {
        
    },
}
</script>