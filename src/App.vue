<template>
  <div class="card" :style="{width:400+'px',position:'absolute',left:'50%',top:'50%',transform:'translate(-50%,-50%)'}">
    <Header :titleHeader="titleHeader"></Header>
    <Body @AllItem="myItems" :itemArray="items" :textStrng="text"></Body>
    <Footer :kontrolDot="items"></Footer>
  </div>
</template>

<script>
  import Header from "./Header.vue";
  import Body from "./Body.vue";
  import Footer from "./Footer.vue";
  export default{
    data : function(){
      return{
        items : [],
        text : "",
        titleHeader : "Vue.js To Do Application"
      }
    },

    methods : {
      myItems : function(e){
        this.items = e;
        return this.items
      }
    },

    components : {
      Header : Header,
      Body : Body,
      Footer : Footer
    }
  }
</script>