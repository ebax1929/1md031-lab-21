<template>



  <header>
    <div id="header_image">
      <img src="https://www.northernoutdoors.com/wp-content/uploads/2020/10/xlodge-lounge-bar-e1603738215527.jpg.pagespeed.ic.ZNSrVMBqlw.jpg" style="width:100%;height:250px" alt="header" >
    </div>
    <h1 id="id_header">Välkommen till <i>Smarriga Hamburgare</i></h1>
  </header>
  <nav id="id_info">
    <b>
      Här kan du beställa hem de godaste burgarna STS-programmet har att erbjuda!
  </b></nav>
  <hr>
  <main style="background-color:#8FBC8F">
    <section id="id_BURGARE" >
      <div class="wrappers">
        <Burger v-for="burger in burgers"
                v-bind:burger="burger"
                v-bind:key="burger.name"
                v-on:orderedBurger="addToOrder($event)"
                v-bind:style="{}"/>
      </div>

    </section >
    <hr>
    <section id="id_kunduppgifter">
      <div>
        <b>Fyll i dina uppgifter för att beställa</b><br />
        <p>
          <label for="Name">Namn</label><br>
          <input type="text" id="Name" v-model="Name" required="required" placeholder="First and last name" >
        </p>
          <span>{{ Name }}</span>
        <p>
          <label for="E-mail">E-mail</label><br>
          <input type="email" id="E-mail" v-model="Email" required="required" placeholder="E-mail address" >
        </p>
        <span>{{ Email }}</span>
<!--        <p>
          <label for="Street">Street</label><br>
          <input type="text" id="Street" v-model="Street" required="required" placeholder="Street" >
        </p>
        <span>Street: {{ Street }}</span>
        <p>
          <label for="House number">Husnummer</label><br>
          <input type="number" id="House number" v-model="HouseNumber" required="required" placeholder="House number" >
        </p>
          <span>HouseNumber: {{ HouseNumber }}</span>-->


      <p>
          <label for="Payment Method"> Choose Payment Method </label> <br />
          <select id="Payment Method" v-model="SelectPayment">
            <option>Credit-card</option>
            <option>Swish</option>
            <option>Klarna</option>
            <option>Invoice</option>
            <span>SelectPayment: {{ SelectPayment }}</span>
          </select>
      </p>

          <label for="gender">Gender</label><br />
          <input type="radio" checked="checked" id="gender" v-model="gender" required="required" placeholder="Woman" value="Woman"> Woman<br />
          <input type="radio" id="gender" v-model="gender" required="required" placeholder="Man" value="Man"> Man <br />
          <input type="radio" id="gender" v-model="gender" required="required" placeholder="non-binary" value="non-binary"> Non-binary <br />
          <input type="radio" id="gender" v-model="gender" required="required" placeholder="not your business" value="not your business"> Not your business <br />
        <br /><span>{{ gender }}</span>
      </div>
    </section>


   <div id="scroller">
     <div id="map" v-on:click="setLocation">
       click here
     <div v-bind:style="{ left: location.x + 'px', top: location.y + 'px'}">
       T
    </div>
     </div>
   </div>

    <div id="orders" class="button">
      <button v-on:click="markDone(key)">Place your order</button>
    </div>

  </main>
    <br />
  <hr>
  <footer>
    <hr>
    &copy; Smarriga "Humbug"are
  </footer>

</template>

<script>
import Burger from '../components/Burger.vue'
import io from 'socket.io-client'
import menu from '../assets/menu.json'

const socket = io();

export default {
  name: 'Home',
  components: {
    Burger
  },
  data: function () {
    return {
      burgers:menu,
      Name:'',
      Email:'',
      SelectPayment:'',
      gender:'',
      orderedBurgers:{},
      location: { x: 0, y: 0}
    }
  },
  methods: {
    getOrderNumber: function () {
      return Math.floor(Math.random()*100000);
    },
    addToOrder: function (event) {
      return this.orderedBurgers[event.name] = event.amount;
    },

    addOrder: function () {
    },

    setLocation: function(event) {
      var offset = {x: event.currentTarget.getBoundingClientRect().left,
                    y: event.currentTarget.getBoundingClientRect().top};
      this.location= { x: event.clientX - 10 - offset.x,
                       y: event.clientY - 10 - offset.y };
    },
    markDone: function() {
      socket.emit("addOrder", {
            orderId: this.getOrderNumber(),
            orderItems: this.orderedBurgers,
            details: { x: this.location.x,
                       y: this.location.y,
                       Name: this.Name,
                       Email: this.Email,
                       SelectPayment: this.SelectPayment,
                       Gender: this.gender},
      });
      console.log("Name:", this.Name,"Email:", this.Email,"Payment Method:",this.SelectPayment, "Gender:",this.gender, "Ordered Burgers:", this.orderedBurgers)

    },
  }
}
</script>

<style>

  #scroller {
  overfloW: scroll ;
    width: 400px;
    height: 300px;
    margin-bottom: 20px;
}

  #map {
    position: relative;
    margin: 0;
    padding: 0;
    background: url("/img/polacks.jpg");
    background-repeat: no-repeat;
    width: 1920px;
    height: 1078px;
    cursor: crosshair;
  }
  #map div {
    position: absolute;
    background: black;
    color: white;
    border-radius: 10px;
    width:20px;
    height:20px;
    text-align: center;
  }

  body {
    font-family: arial;
  }

  #id_BURGARE {
    border-radius: 10px;
    border: 5px solid #8FBC8F;
    background-color: #000000;
    color: white;
  }

  #id_kunduppgifter {
    border: 3px double #000000;
    border-radius: 10px;
    padding: 20px;
  }
  button:hover {
    cursor: pointer;
    color: #D2691E;
  }
  .button {
    width: 150px;
    height: 75px;
    padding-left:20px;
    padding-bottom:20px;
  }
  
  #header_image {
    opacity: 0.5 ;
  }

  #id_header {
    opacity: 1 ;
    color: #FFFFFF;
    position: absolute;
    top: 80px;
    right: 30;
    width: 1000px;
    height: 20 ;
    overflow: hidden
  }

  #id_info {
    opacity: 1 ;
    color: #FFFFFF;
    position: absolute;
    top: 160px;
    right: 30;
    width: 1000px;
    height: 20;
    overflow: hidden
  }

  #id_button {
    margin: 20px 5px 20px 5px;
  }

  .wrappers {
    display: grid;
    grid-gap: 1px;
    grid-template-columns: 33% 33% 33%;
    grid-template-rows: 100%;
    background-color: #8FBC8F;
    color: #444;
  }

  .box {
    background-color: #000000;
    color: white;
    border: 3px double #8FBC8F;
    border-radius: 10px;
    padding: 10px;
    font-size: 100%;
    font-family: arial;
  }
  .box_burgare {
    background-color: #000000;
    color: white;
    border-radius: 25px;
    border: 3px double #556B2F;
    padding: 10px;
    font-size: 100%;
    font-family: arial;
  }

  #id_BURGARE > div {
    padding-left:2px  ;
  }
  #id_kunduppgifter > div {
    padding-top: 20px ;
    padding-left: 20px    ;
  }



</style>
