<template>
<div class="content">
  <div class="textdiv">
      <p class="text">{{ content }}</p>
  </div >
      <button @click="newQuote" class="btn">Hit me with a new one</button>
</div>
</template>

<script>
export default {
    data(){
        return{
            content: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsa, necessitatibus hic dicta quam dolore modi. Voluptate, animi repellat deleniti accusantium aspernatur quidem eum. Voluptatum officia voluptate, deserunt voluptates quo tenetur illo corporis nesciunt, doloremque quas amet deleniti laudantium nulla ullam error ducimus suscipit autem porro? Eos iure ad natus sapiente!',
        }
    },
     methods:{
        async getData(){
            const res = await fetch('https://api.kanye.rest/')
            const data = await res.json()
            return data
        },
        async newQuote(){
            const inc = await this.getData()
            this.content = inc['quote']
        },
    },

    async mounted(){
            const inc = await this.getData()
            this.content = inc['quote']
        }
}

</script>

<style>
p{
    font-size: 20px;
    text-align: center;
}

.textdiv{
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 80px;
    word-wrap: break-word;
}
.content{
    
    width: 25em;
    height: 300px;
    flex-direction: column;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #ADD9F4;
    border-radius: 10%;
    padding: 15px;
    box-shadow: 10px 20px 15px rgb(97, 95, 95);
	border-radius: 20px;
}
@media only screen and (max-width: 600px) {
  .content {
      width: 12em;
}
}
button{
    margin-top: auto; 
    height: 50px;
    width: max-content;
    padding: 15px;
    background-color: #984447;
    border-radius: 10%;
    color: white;
}
button:hover{
        background-color: #b97173;
        transition: 0.2 ease;

}



</style>