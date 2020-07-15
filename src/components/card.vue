<template>
    <div class="card">
      <div class="card-content ">
          <li class="ele has-text-white">Name: {{name}}</li>
          <li class="ele has-text-white">Date: {{date}}</li>
          <li class="ele has-text-white">Diameter: {{diameter}}</li>
          <li class="ele has-text-white">Distance: {{distance}}</li>
      </div>
    </div>
</template>

<script>


export default {
    name:"Card",
    components:{
    },
    props:{
        name: String,
        id:String,
        date:String,
        diameter:Number,
        distance:String
    }

}
</script>

<style >
.card{
  margin:20px !important;
}
li{
  list-style: none;
}
</style>