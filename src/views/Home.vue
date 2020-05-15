<template>
  <div class="home">
      
      <div class="container z-depth-4">
        <img :src="img" class="img"> 
        <div class="personal-data">
          
          <div class="name style">
            <span>{{name_f}} {{name_l}}</span>  
          </div>  
          
          <div class="location style">
            <div class="icon">
                <span>
                    <i class="material-icons">home</i>
                </span>
                <span>{{postcode}} {{street}},</span>
            </div>
                <span>{{street}} {{street_num}}, {{country}}</span>
              
          </div>
          
          <div class="contact style">
              <div class="cont phone">
                  <span>
                      <i class="material-icons">local_phone</i>
                  </span>
                  <span>
                     {{phone}}
                  </span>
              </div>
              <div class="cont email">
                  <span>
                      <i class="material-icons">email</i>
                  </span>
                  <span>
                      {{email}}
                  </span>
            </div>
            
            
          </div>
        </div> 
        <div class="btn z-depth-3" v-on:click.prevent="nextProfile">
          <span v-if="data">NEXT</span>
          <span v-else>START</span>
        </div>
      </div> 
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'Home',
  data(){
    return{
      data: false,
      name_f: null,
      name_l:null,
      email: null,
      phone: null,
      img: null,
      city: null,
      postcode: null,
      street: null,
      street_num:null,
      country: null
    }
  },methods: {
    nextProfile(){
      this.data = true

      axios.get('https://randomuser.me/api')
      .then(response => {
          console.log(response)
          this.email = response.data.results[0].email,
          this.img = response.data.results[0].picture.large,
          this.name_f = response.data.results[0].name.first,
          this.name_l =  response.data.results[0].name.last,
          this.phone = response.data.results[0].phone,
          this.city = response.data.results[0].location.city,
          this.postcode = response.data.results[0].location.postcode,
          this.street = response.data.results[0].location.street.name,
          this.country = response.data.results[0].location.country,
          this.street_num = response.data.results[0].location.street.number
      })
    }
  },
  created() {
    
      
    
  }
  
}
</script>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&display=swap');

  .home .container{
    /* border: 1px solid black; */
    border-radius: 10px;
    width: 380px;
    margin: 10px auto;
    margin-bottom: 40px;
    padding: 10px;
    position: relative;
    top: 150px;
    background: linear-gradient(45deg, dimgray, #e0e0e0);
  }

  .home .container .img {
      display: block;
      height: 320px;
      width: 270px;
      border-radius: 7px;
      margin: 20px auto;
      padding: 10px 5px;
      border: 1px solid black;
      background: linear-gradient(45deg, black, grey);
  }

  .home .container .personal-data .style{
    font-size: 20px;
    font-family: 'Amatic SC', cursive;
    font-weight: 700;
    letter-spacing: 0.1em;
    padding: 5px 40px;
  }

  .home .container .personal-data .location .icon{
    display: flex
  }
  .home .container .personal-data .location .icon span{
    padding: 3px;
  }
   .home .container .personal-data .name{
     font-size: 30px;
    
     text-align: center
   }

  .home .container .personal-data .contact .cont{
    display: flex;
    border-top: 1px solid grey;
    
  }

  .home .container .personal-data .contact .cont span{
    padding: 3px;
  } 

  .home .container .btn{
    display: block;
    margin: 10px 10px;
    padding: 4px 0;
    border-radius: 4px;
    background: linear-gradient(45deg, black, gold) ;
    font-family: 'Amatic SC', cursive;
    font-weight: 700;
    font-size: 28px;
  }


</style>
