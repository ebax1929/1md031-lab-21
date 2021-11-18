<template>

  <div>
    Burgers
    <Burger v-for="burger in burgers"
            v-bind:burger="burger"
            v-bind:key="burger.name"/>
  </div>
  <div id="map" v-on:click="addOrder">
    click here
  </div>

  <header>
    <div id="header_image">
      <img src="https://www.northernoutdoors.com/wp-content/uploads/2020/10/xlodge-lounge-bar-e1603738215527.jpg.pagespeed.ic.ZNSrVMBqlw.jpg" style="width:100%;height:250px" alt="header" >
    </div>
    <h1 id="id_header">Välkommen till <i>Smarriga Hamburgare</i></h1>
  </header>
  <nav id="id_info"> <b>Här kan du beställa hem de godaste burgarna STS-programmet har att erbjuda</b><br /> </nav>
  <hr>
  <main>
    <section id="id_BURGARE" class="wrapper">
      <br />
      <br />
      <div class="box_burgare class_göteborg">
        <b> Göteburgarn</b>
        <br />
        <br />
        <img src="https://img.hellofresh.com/f_auto,fl_lossy,q_auto,w_1200/hellofresh_s3/image/halloumiburgare-2e7f906b.jpg" style="width:300px;height:300px" alt="Göteburgare" >
        <p> Göteburgarn är en maxad burgare <br />
          med potatobun,halloumipatty, <br />
          picklad rödlök, grönsallat och avokado
        </p>
        <ul>
          <li>Vegansk</li>
          <li><section class="class_allergener">
            <p>Innehåller <span id="id_allergener"> gluten</span></p>
          </section></li>
        </ul>
      </div>
      <div class="box_burgare class_kungsbacka">
        <b> Kungsbacka Fjorden </b><br /><br />
        <img src="https://cdn-rdb.arla.com/Files/arla-se/4157482549/b5e7081d-32b2-4675-b3ca-8f01f742d723.jpg?mode=crop&w=1200&h=630&scale=both&format=jpg&quality=80&ak=f525e733&hm=35af1404" style="width:300px;height:300px" alt="kungsbacka fjorden"  >
        <p> Fjordburgarn, ett fluffigt baugettbröd <br />
          fullproppad med färsk panerad fisk från <br />
          västkusten, bostongurka, dill, grönsallat, <br />
          tomat och skagenröra.
        </p>
        <ul>
          <li>Pesctiariansk</li>
          <li> <section class="class_allergener">
            <p>Innehåller <span id="id_allergener">laktos </span></p>
          </section></li>
        </ul>
      </div>
      <div class="box_burgare class_uppsala">
        <b> Uppsalas slottsburgare </b><br /><br />
        <img src="https://folkofolk.se/sites/default/files/2021-08/klassisk-hamburgare_2.jpg" style="width:300px;height:300px" alt="uppsalaslotts burgare" >
        <p> Slottsburgarn är en klassisk <br />
          burgare och består av briochebun <br />
          fylld med en högrevspatty,cheddarost,<br />
          våregna dressing, pickles och grönsallat.
        </p>
        <ul>
          <li> <section class="class_allergener">
            <p>Innehåller <span id="id_allergener"> gluten och laktos </span></p>
          </section></li>
        </ul>
      </div>
      <div class="box class_extra">
        <dl>
          <dt><b>Extra Önskemål?</b></dt>

          <dd>Det går att få alla burgare veganska med vår plantbaserade patty,
            eller byta ut olika delar för att anpassa till allegier.</dd>

          <dd>Är du en baconälskare, lägg till 4 skivor för bara 10kr!</dd>

          <p><label> for="Extra Bacon">Extra Bacon</label><br>
            <input type="radio" id="Extra Bacon" name="ln" placeholder="Extra Bacon"></p>

          <p><label for="Vegansk Patty">Vegansk Patty</label><br>
            <input type="radio" id="Vegansk Patty" name="ln" placeholder="Vegansk Patty"></p>
        </dl>
      </div>
    </section >
    <hr>
    <section id="id_kunduppgifter">
      <div>
        <b>Fyll i dina uppgifter för att beställa</b><br />
        <p>
          <label for="Namn">Namn</label><br>
          <input type="text" id="Namn" name="fn" required="required" placeholder="För och Efternamn" >
        </p>
        <p>
          <label for="E-mail">E-mail</label><br>
          <input type="email" id="E-mail" name="em" required="required" placeholder="E-mail address" >
        </p>
        <p>
          <label for="Gata">Gata</label><br>
          <input type="text" id="Gata" name="ln" placeholder="Gata" >
        </p>
        <p>
          <label for="Husnummer">Husnummer</label><br>
          <input type="number" id="Husnummer" name="em" required="required" placeholder="Husnummer" >
        </p>


      <p>
          <label for="Betalningsmetod"> Välj Betalningsmetod </label> <br />
          <select id="Betalningsmetod" name="Betalningsmetod">
            <option>Betala med kort</option>
            <option>Betala med swish</option>
            <option>Betala med Klarna</option>
            <option>Betala med faktura</option>
          </select>
      </p>

          <label for="Kön">Kön</label><br />
          <input type="radio" checked="checked" id="Kön" name="em" required="required" placeholder="Kvinna" value="Kvinna"> Kvinna<br />
          <input type="radio" id="Kön" name="em" required="required" placeholder="Man" value="Man">Man <br />
          <input type="radio" id="Kön" name="em" required="required" placeholder="Icke-binär" value="Icke-binär">Icke-binär <br />
          <input type="radio" id="Kön" name="em" required="required" placeholder="Vill inte ange" value="Vill inte ange"> Vill inte svara <br />
      </div>
    </section>

        <button type="submit" id="id_button">
        Placera din order <br />
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/71/Arrow_east.svg/2560px-Arrow_east.svg.png" style="width:30px;height:20px" alt="pil">
      </button>

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

const socket = io();

function MenuItem(name, url, lactose, gluten, kcal) {
  this.name = name;
  this.url = url;
  this.lactose = lactose;
  this.gluten = gluten;
  this.kcal= kcal;
}

export default {
  name: 'Home',
  components: {
    Burger
  },
  data: function () {
    return {
      burgers: [
        new MenuItem('Göteburgarn', 'pic', "False", "True","300"),
        new MenuItem("KungsbackaFjorden", "pic","True","False", "400"),
        new MenuItem("UppsalasSlottsburgare", "pic", "True", "True", "500")
      ]
    }
  },
  methods: {
    getOrderNumber: function () {
      return Math.floor(Math.random()*100000);
    },
    addOrder: function (event) {
      var offset = {x: event.currentTarget.getBoundingClientRect().left,
                    y: event.currentTarget.getBoundingClientRect().top};
      socket.emit("addOrder", { orderId: this.getOrderNumber(),
                                details: { x: event.clientX - 10 - offset.x,
                                           y: event.clientY - 10 - offset.y },
                                orderItems: ["Beans", "Curry"]
                              }
                 );
    }
  }
}
</script>

<style>
  #map {
    width: 300px;
    height: 300px;
    background-color: red;
  }

  body {
    font-family: arial;
  }
  .class_allergener {
    color: #DAA520;
  }

  .class_BURGARE {
  }
  #id_BURGARE {
    border-radius: 25px;
    border: 5px solid #FFFFFF;
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

  .wrapper {
    display: grid;
    grid-gap: 30px;
    grid-template-columns: 360px 360px 360px;
    background-color: #fff;
    color: #444;
  }

  .box {
    background-color: #000000;
    color: white;
    border: 3px double #8FBC8F;
    border-radius: 10px;
    padding: 20px;
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

  .class_göteborg {
    grid-column: 1;
    grid-row: 1;
  }
  .class_kungsbacka {
    grid-column: 2;
    grid-row: 1;
  }

  .class_uppsala {
    grid-column: 3;
    grid-row: 1;
  }
  .class_extra {
    grid-column: 1/2;
    grid-row: 2;
  }
  #id_BURGARE > div {
    padding-left:30px  ;
  }
  #id_kunduppgifter > div {
    padding-top: 20px ;
    padding-left: 20px    ;
  }
</style>
