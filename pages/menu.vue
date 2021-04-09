<template>

    <div class="menu">
      <main id="main-content" class="row justify-content-center mb-5">
        <div class="accordion accordion-width" role="tablist">
          <h2 class="text-uppercase text-center mb-5 mt-4">Menu</h2>
          <!-- REWROTE ACCORDION WITH BOOTSTRAP VUE -->
          <b-card no-body class="mb-1">
            <b-card-header header-tag="header" class="p-1" role="tab">
              <b-button class="btn btn-link" block v-b-toggle.accordion-1 variant="link"><h3 class="my-3">Coffee</h3></b-button>
            </b-card-header>
            <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel">
              <b-card-body class="card-body row">
                <!----V-FOR---->
                <div class="col-12 col-sm-6 col-md-4 col-lg-4 mb-4" v-for="drink in coffeeDrinks" v-bind:key="drink.id" :item="drink.item" :priceSmall="drink.priceSmall" :priceLarge="drink.priceLarge">
                  <h5>{{drink.item}}</h5>
                  <ul class="list-inline d-flex flex-column">
                    <li class="list-inline-item">Small {{drink.priceSmall}}</li>
                    <li class="list-inline-item">Large {{drink.priceLarge}}</li>
                  </ul>
                </div>
              </b-card-body>
            </b-collapse>
          </b-card>

          <b-card no-body class="mb-1">
            <b-card-header header-tag="header" class="p-1" role="tab">
              <b-button class="btn btn-link" block v-b-toggle.accordion-2 variant="link"><h3 class="my-3">Food</h3></b-button>
            </b-card-header>
            <b-collapse id="accordion-2" accordion="my-accordion" role="tabpanel">
              <b-card-body class="card-body row">
                 <!----V-FOR---->
                <div class="col-12 col-sm-6 col-md-4 col-lg-4 mb-4" v-for="food in foodItems" v-bind:key="food.id" :item="food.item" :price="food.price">
                  <h5>{{food.item}}</h5>
                  <ul class="list-inline d-flex flex-column">
                    <li class="list-inline-item">{{food.price}}</li>
                  </ul>
                </div>
              </b-card-body>
            </b-collapse>
          </b-card>

          <b-card no-body class="mb-1">
            <b-card-header header-tag="header" class="p-1" role="tab">
              <b-button class="btn btn-link" block v-b-toggle.accordion-3 variant="link"><h3 class="my-3">Other</h3></b-button>
            </b-card-header>
            <b-collapse id="accordion-3" accordion="my-accordion" role="tabpanel">
              <b-card-body class="card-body row">
                <!----V-FOR---->
                <div class="col-12 col-sm-6 col-md-4 col-lg-4 mb-4" v-for="drink in otherDrinks" v-bind:key="drink.id" :item="drink.item" :priceSmall="drink.priceSmall" :priceLarge="drink.priceLarge">
                  <h5>{{drink.item}}</h5>
                  <ul class="list-inline d-flex flex-column">
                    <li class="list-inline-item">Small {{drink.priceSmall}}</li>
                    <li class="list-inline-item">Large {{drink.priceLarge}}</li>
                  </ul>
                </div>
              </b-card-body>
            </b-collapse>
          </b-card>
        </div>
      </main>
    </div>
  
</template>


<script>
export default {
  name: 'Menu',
  data () {
    return {
      title: 'Ten Ton Coffee - Menu',
      coffeeDrinks: [
        {id: 0, item: 'Drip Coffee', priceSmall: '2.50', priceLarge: '2.90'},
        {id: 1, item: 'Americano', priceSmall: '2.50', priceLarge: '2.90'},
        {id: 2, item: 'Latte', priceSmall: '2.50', priceLarge: '2.90'},
        {id: 3, item: 'Iced Latte', priceSmall: '4.75', priceLarge: '5.25'},
        {id: 4, item: 'Caramel Macchiato', priceSmall: '4.25', priceLarge: '4.75'},
        {id: 5, item: 'Mocha', priceSmall: '4.50', priceLarge: '5.00'}
      ],
      foodItems: [
        {id: 0, item: 'Crossaint', price: '3.35'},
        {id: 1, item: 'Pain Au Chocolat', price: '3.85'},
        {id: 2, item: 'Apple Turnover', price: '4.35'},
        {id: 3, item: 'Raspberry Donut', price: '3.40'},
        {id: 4, item: 'Chocolate Chip Cookie', price: '2.75'},
        {id: 5, item: 'Ginger Chew Cookie', price: '3.65'}
      ],
      otherDrinks: [
        {id: 0, item: 'Chai Tea Latte', priceSmall: '4.40', priceLarge: '4.70'},
        {id: 1, item: 'London Fog', priceSmall: '3.25', priceLarge: '3.75'},
        {id: 2, item: 'Green Tea Matcha Latte', priceSmall: '4.40', priceLarge: '4.95'},
        {id: 3, item: 'Soft Drinks', priceSmall: '2.75', priceLarge: '3.25'},
        {id: 4, item: 'Perrier', priceSmall: '3.10', priceLarge: '3.75'},
        {id: 5, item: 'Orangina', priceSmall: '3.50', priceLarge: '4.00'}
      ]
    }
  },
  head () {
      return {
        title: this.title,
        meta: [
          // hid is used as unique identifier. Do not use `vmid` for it as it will not work
          {
            hid: 'description',
            name: 'description',
            content: 'Ten Ton Coffee - Menu'
          }
        ]
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

.accordion-width {
  width: 75vw;
}

</style>