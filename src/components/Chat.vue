<template>
  <div class="container">
    <div v-for="mensagem in mensagens" :key="mensagem">
      <Message
        :my_user="my_user"
        :mensagem="mensagem" />
    </div>
  </div>
</template>


<script>
  import Message from './Message.vue';
  export default{
    name: 'Chat',
    components:{
      Message
    },
    data: function(){
      return {
        my_user: 'joao',
        mensagens: [
          {
            user:{
              img: "/favicon.ico",
              nome: 'joao'
            },
            text: 'teste1',
            hora: '11:00'
          },
          {
            user:{
              img: "/favicon.ico",
              nome: 'pedro'
            },
            text: 'teste2',
            hora: '12:00'
          }
        ]
      }

    }
  }
</script>
