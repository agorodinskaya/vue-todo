<template>
<div class="container">
  <Header title="task tracker"/>
  </div>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header,
  },
  data() {
    return {
      tasks : []
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 50vw;
  margin: 30px auto;
  overflow: auto;
  min-height: 50vh;
  border: 1px solid #b446af;
  padding: 30px;
  border-radius: 5px;
  box-shadow: 3px 3px #2503204d;
}
.btn {
  display: inline-block;
  background: #08022ce0;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:hover {
  background: #840af7a1;
  color: #250320;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
