<template>
  <div>
    {{ burger.name }} {{ burger.kCal }}
  </div>

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
</template>

<script>
export default {
  name: 'Burger',
  props: {
    burger: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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

</style>
