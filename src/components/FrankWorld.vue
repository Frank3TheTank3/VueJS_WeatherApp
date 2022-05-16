<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      As developers we need a stable framework. Super Vue is my custom version that is perfect
      for long hours of web development. Join the movement now and get a bonus coupon for 
      online purchases.
    </p>
    <h1>Main features of Super Vue:</h1>

    <h3>Easy to use</h3>
    <h3>Lots of options</h3>
    <h3>Modern framework</h3>
    <h3>Vue JS base but made by Frank</h3>
    <input type="text" name="vueinput" id="" value="">
   
  </div>
</template>

<script>
export default {
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
