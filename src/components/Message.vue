<template>
  <div class="container">
    <img :src="mensagem.user.img" :class="this.message_side" :alt="mensagem.user.img">{{mensagem.user.nome}}
    <p>{{mensagem.text}}</p>
    <span :class="this.time_side" >{{mensagem.hora}}</span>
  </div>
</template>

<script>
export default{
  name: 'Message',
  props:{
    mensagem: Object,
    my_user: String
  },
  mounted: function(){
    if(this.mensagem.user.nome === this.my_user){
      this.message_side = 'right';
      this.time_side = 'time-right';
    }else{
      this.message_side = 'left';
      this.time_side = 'time-left';
    }
  },
  data:  function(){
    return {
      message_side: ''
    }
  }
}
</script>

<style>
/* Chat containers */
.container {
 border: 2px solid #dedede;
 background-color: #f1f1f1;
 border-radius: 5px;
 padding: 10px;
 margin: 10px 0;
}

/* Darker chat container */
.darker {
 border-color: #ccc;
 background-color: #ddd;
}

/* Clear floats */
.container::after {
 content: "";
 clear: both;
 display: table;
}

/* Style images */
.container img {
 float: left;
 max-width: 60px;
 width: 100%;
 margin-right: 20px;
 border-radius: 50%;
}

/* Style the right image */
.container img.right {
 float: right;
 margin-left: 20px;
 margin-right:0;
}

/* Style time text */
.time-right {
 float: right;
 color: #aaa;
}

/* Style time text */
.time-left {
 float: left;
 color: #999;
}
</style>
