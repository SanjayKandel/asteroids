<template>
    <section class="section">
        <div class="container search-container">
            <div class="columns ">
                    <div class="column is-three-quarters ">
                        <input type="text" class="input is-rounded input-field " placeholder="">
                    </div>
                    <div class="column">
                        <button class="button">Search</button>
                    </div>
                        
            </div>
        </div>
        <div class="container data-container">
        <div class="columns is-gapless is-multiline is-mobile" v-for="(value,name) in asteroidData" v-bind:key="name.id">
            <div class="column is-one-third-desktop is-half-tablet is-full-mobile "  v-for="item in value" v-bind:key="item.id">
                <Card 
                :name="item.name" 
                :id="item.id" 
                :date="item['close_approach_data'][0]['close_approach_date']"
                :distance="item['close_approach_data'][0]['miss_distance']['astronomical']"
                :diameter="item['estimated_diameter']['kilometers']['estimated_diameter_max']"
                />
            </div>
        </div>
        </div>
    </section>
</template>

<script>
import Card from "./card";
import axios from 'axios';
export default {
    name:"Container",
    components:{
        Card
    },
    data(){
        return {
        asteroidData:{}

        }
    },
    created(){
        let fullDate=new Date();
        let startDate = fullDate.getFullYear()+'-'+(fullDate.getMonth()+1)+'-'+fullDate.getDate();
        axios.get(`https://www.neowsapp.com/rest/v1/feed?start_date=${startDate}&end_date=&detailed=false&api_key=rXdB2R2Am14AgjTOBPDYMoiPd58C8sSJ90ZZPi7q`)
        .then(response => (this.asteroidData=response.data['near_earth_objects']))
        .catch(err=>(console.log(err)));
        
    },
    methods: {

    }
}
</script>


<style  scoped>

.section{
    background-color: #100e17 !important;
    margin:0px;
    padding:0px !important;
}
.search-container{
    padding:40px;
}
.input-field{
    width:80%;
    float:right;
}

</style>
