<template>
  <div>
    <h1 class="mainHeader">Welcome to Geniusify-Quiz</h1>
    <h2 class="chooseNameText">Choose your name!</h2>
    <input type="text" v-model="name" v-on:keydown.enter="submit" autofocus placeholder="Name">
    <button @click="submit">SUBMIT</button>
    <i class="cd-icon fas fa-compact-disc"></i>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      name: ""
    };
  },
  methods: {
    submit() {
      // Method for submitting the chosen name
      if (this.name === "") {
        this.name = "Anonymous"; // if the user does choose a name
      } else if (this.name.length > 10) {
        this.name = this.name.substring(0, 10); // Shortens the username if it is to long.
      }
      this.$emit("nameChoosen", this.name);
    }
  }
};
</script>

<style scope>
.mainHeader {
  text-transform: uppercase;
  font-size: 3.4rem;
  font-weight: 400;
  color: #ed4c67;
}

.chooseNameText {
  color: white;
  font-weight: 200;
}

input {
  border: none;
  background-color: rgba(255, 255, 255, 0.4);
  color: white;
  width: 50%;
  height: 100px;
  font-size: 80px;
  text-align: center;
  -webkit-box-shadow: 0px 0px 30px -2px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 0px 0px 30px -2px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 30px -2px rgba(0, 0, 0, 0.5);
}

button {
  cursor: pointer;
  color: white;
  font-size: 2rem;
  background: #ed4c67;
  padding: 1.1rem;
  margin: 1rem;
  border-radius: 1rem;
  -webkit-box-shadow: 0px 0px 30px -2px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 0px 0px 30px -2px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 30px -2px rgba(0, 0, 0, 0.5);
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-top: 1rem;
}

button:active {
  animation: blur 1s 1;
  transition: 1s;
}

button:hover {
  background-color: white;
  color: #ed4c67;
}

.cd-icon {
  margin-top: 2.4rem;
  font-size: 19rem;
  color: #ed4c67;
  animation-name: rotate;
  animation-duration: 20s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
