<!--
    <img v-bind:src="logo" :width="logowidth" />
    <h1 :style="colors">{{ welcome }}</h1>

    <HelloWorld msg="This is Super Vue. The next level of web design framework in 2022."/>
     <h1>{{ order}} {{ price}}  {{ currency}} </h1> 

    <input v-model="welcome" />

    <br />
    <label for="lessontype">Choose your lesson for Opportunity</label>
    <br />

    <input id="lessontype" v-model="lesson" />

    <div v-if="lesson === 'HTML'">You chose HTML</div>
    <div v-else-if="lesson === 'CSS'">You chose CSS</div>
    <div v-else-if="lesson === 'PHP'">You chose PHP</div>
    <div v-else-if="lesson === 'Node JS'">You chose Node JS</div>
    <div v-else-if="lesson === 'Python'">You chose Python</div>
    <div v-else-if="lesson === 'Angular'">You chose Angular</div>
    <div v-else>You will be learning something else with us</div>

    <label
      >Select your lesson:
      <select v-model="lesson">
        <option value="PHP">PHP</option>
        <option value="CSS">CSS</option>
        <option value="HTML">HTML</option>
      </select>
    </label>

    <br />

    <button @click="inStock = !inStock">Toggle</button>

    <br />
    <p v-if="inStock">There is only one lesson left</p>
    <p v-else>Oh no 😢 all lesson for Opportunity have been booked</p>

    -->
    
    /*
      lesson: "Python",
      welcome: "Welcome to Opporunity the best IT education in ZH",
      order: "Buy a brand new PS5 with the Frank Web-App for",
      price: 500,
      currency: "CHF",
      logo: require("../src/assets/logo_op2.png"),
      logowidth: 1000,
      showlessons: [1, 2, 3, 4, 5],
      primarycol: "orange",
      inStock: true,
      colors: {
        color: "orange",
        backgroundColor: "white",
      },
      */


      /*
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-image: url("https://thumbs.gfycat.com/BraveOptimalBaleenwhale-size_restricted.gif");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  margin-top: 60px;
  height: 1000px;
}

input {
  height: 25px;
  width: 800px;
  font-size: 20px;
}
*/