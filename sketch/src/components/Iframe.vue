<template>
<div>
    <form class="example" @click.prevent="search" style="margin:auto;max-width:300px">
    <input type="text" v-model="searchs" placeholder="Search.." name="search2">
    <button type="submit"><i class="fa fa-search"></i></button>
    </form>
 <div>
<iframe class="container"  id="api-frame" allow="autoplay; fullscreen; vr" allowvr allowfullscreen mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</div>
</div>
</template>
<script>
export default {
    name:"Iframe",
    data(){
        return {
            searchs:"",
            models:
            {
                tajmahal:'ikI3rGTwIf9xdRrcEgxTxEywGH3',
                apple:'7306582923d5481bab4dd8844051e502',
                albert:'3f9b2934b4ee44969b29cce2ce46e13f',
                bob:'7w7pAfrCfjovwykkEeRFLGw5SXS',
                ironman:'d87547f21f904cfa954f4cf77a1409ac',
                london:'a7497c33ce4c493696fdd40ec0437301',
                india:'c86b16b141e54d2d844b740941bedb0c',
                bike:'446d2f54cf6346a89afa9a9578c4c9cd',
                charterhouse:'21b7cc89dd0c4c0487575f8af4dc7713',
                goku:'35edf16494e74f5d9c96f3d11c476162',
                rajinikanth:'584a0230ff184ffabc20af0e7fe3deb4',
                america:'9f91319b16f14de780d444422eff63ad',
                newyork:'271e4593fa9d43a7820aa3539d7d15e4',
                rain:'7036afaa134c464a9e8a2dbd46f9919d',
            },
            uid:"",
        }},
        methods:{
            search(){
            let i=0;

            for (i in this.models){
                if(i==this.searchs)
                {
                    this.uid=this.models[i]
                }
                
            }
        var iframe = document.getElementById( 'api-frame' );
        // var uid = '7w7pAfrCfjovwykkEeRFLGw5SXS';
        var client = new window.Sketchfab( iframe );
        console.log(iframe)
        client.init( this.uid, {
        success: function onSuccess( api ){
            api.start(
                

                
            );
            api.addEventListener( 'viewerready', function() {
                console.log( 'Viewer is ready' );

            } );
        },
        error: function onError() {
            console.log( 'Viewer error' );
        }
    } );
        }   
}
            
        }    
</script>

<style scoped>
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css";

* {
  box-sizing: border-box;
}
.container {
    margin-top:15px;
    width:98vw;
    height:88vh;
    border-radius:15px;
    }
form.example input[type=text] {
  padding: 10px;
  font-size: 17px;
  border: 1px solid grey;
  float: left;
  width: 80%;
  background: #f1f1f1;
}

form.example button {
  float: left;
  width: 20%;
  padding: 10px;
  background: #2196F3;
  color: white;
  font-size: 17px;
  border: 1px solid grey;
  border-left: none;
  cursor: pointer;
}

form.example button:hover {
  background: #0b7dda;
}

form.example::after {
  content: "";
  clear: both;
  display: table;
}
</style>