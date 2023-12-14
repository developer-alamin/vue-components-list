<script setup>
	const props = defineProps(['image','location','price','rating','time',"title"]);
</script>
<template>
    <div class="card col-3">
    	<div class="ImgHoverDiv">
            <img class="card-img-top" :src="image" alt="Card image cap">
          </div>
          <div class="Info mt-1">
            <div class="container">
              <div class="row">
                <div class="col-6">
                  <h6>{{ location }}</h6>
                </div>  
                <div class="col-6">
                 <h6 class="text-right">{{ price }}/Day</h6>
                </div>  
              </div>  
            </div>
          </div>  
          <div class="card-body">
            <h4 class="card-title">{{ title }}</h4>
               <div class="row">
                <div class="col-6">
                  <h6>{{ time }} Days Tour</h6>
                </div>   
              </div>  
          </div>
    </div> 
</template>
<style scoped>
	img.card-img-top {
    height: 300px;
}
.card.col-3 {
    margin-left: 5px;
    margin-right: 5px;
}
div.card{
  padding:0px;
}
img{
   transition:all ease 0.5s;
}
img.card-img-top:hover {
    transform: scale(1.1);
}

div.ImgHoverDiv {
    overflow: hidden;
}
h6.text-right{
  text-align:right;
}
</style>