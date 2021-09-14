<template>
  <div class="input-box">
    <span id="span-box-label" v-html="$t(`signMeInComponent.inputMailLabel`)"></span>
    <input v-model="userInput" type="text" @input="isInputValid(userInput)" id="sign-in-box"><br>
    <span id = "error-msg-span">{{incBoolean ?  " " : $t(`signMeInComponent.errorMessage`)}}</span>
    <div class="send-button">
      <button type="submit" @click="signMeIn()" id="sign-in-button" v-html="$t(`signMeInComponent.signMeButton`)"></button>
    </div>
  </div>
  
</template>

<script>
export default 
{
  name: 'signMeInBoxComponent',

  data() 
  {
    return {
      userInput: " ",
      incBoolean: true,
    }
    
  },

  methods: 
  {
    isInputValid(userInput)
    {
      this.incBoolean = userInput.includes("@");
      console.log(this.incBoolean);
    },

    signMeIn()
    {
      if(this.isInputValid(this.userInput)) 
      {
        console.log("signed in");
      }
      else
      {
        console.log("sorry, not signed in");
      }
    }
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 @import '../styles/signMeInBoxComponentStyle.css';
</style>