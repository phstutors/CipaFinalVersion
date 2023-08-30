<template>
  <div class="content">
    
    <div class="left-side">
      <div class="agroup-content">
        <img src="FundoCipa.png" alt="" srcset="">
        <h2>CIPA WEB</h2>
        <p>Concurso de Ideias <br>Professor Anjo</p>
      </div>
    </div>
    


    <!-- Right side of the page-->
    <div class="right-side">
      <img :src="imageSrc" class="banner">
    <p>Por favor, insira seus <br/>dados para se cadastrar</p>
    <div id="inputs-group">

          <div class="inputs">
            <div class="col-sm-10">
              <label for="staticEmail">Digite seu Email:</label>
              <input type="email" class="form-control" id="staticEmail" placeholder="email@example.com" v-bind:class="{ error: !emailValid }" v-model="email" @input="checkEmail">
              <div id="passwordHelpBlock" class="form-text">
        Use de preferencia seu email discente.
      </div>
              
          </div>
            <div class="senha1">
              <label for="inputPassword5" class="form-label">Digite sua senha:</label>
      <input ref="senha1" v-model="senha" @input="updateImage" type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock" placeholder="">
      <div id="passwordHelpBlock" class="form-text">
        Sua senha tem que ter 8-20 caracteres, e não conter espaço ou emojis.
      </div>
            </div>
      </div>
          </div>

      <button type="button" class="btn btn-primary btn-lg">Entrar</button>
    </div>

  
  </div>

</template>

<style scoped>



.right-side p{
font-size: 15pt;
}
.senha1{
  width: 83%;
}
h2,p{
color: #1E2F40!important;
}.teste {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #F1F4FF;
  font-family: 'Red Hat Display', sans-serif!important;
}

.inputs{
  width: 80%;
  align-items: center;
  justify-content: center;
}

.content {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 8px 10px rgba(0, 0, 0, 0.1);
  border-radius: 42px;
  background-color: #F1F4FF;
  font-family: 'Red Hat Display', sans-serif!important;
}
.animato{
display: flex;
position: relative;
top: -50px;
width: 55px;
left: 86%;

}
.animato img:hover{
  cursor: pointer;
}

.left-side {
  width: 40%;
  height: 70%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: antiquewhite; 
  border-bottom-left-radius: 25px;
 border-top-left-radius: 25px;

}

.right-side {
  width: 40%;
  height: 70%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-items: center;
  border-left: 0.1rem solid black;
  background-color: antiquewhite;
  border-bottom-right-radius: 25px;
 border-top-right-radius: 25px;
}

.agroup-content img{
  width: 320px;
  animation: pulse 8s ease-in-out infinite;
}
.agroup-content h2{
  font-family: 'Red Hat Display', sans-serif;
  font-size: 50pt;
}
.agroup-content p{
  font-family: 'Red Hat Display', sans-serif;
  font-size: 20pt;
}
.right-side img{
width: 270px;
animation: flutuar 2s ease-in-out infinite;
}

#inputs-group{
width: 100%!important;
display: flex;
flex-direction: column;
justify-content: center;
justify-items: center;
align-items: center;
}
.mb-3{
width: 80%!important;
}
.mb-3 input{
  width: 100%;
}
button{
background-color: #4AB7AA;
border: none;
color: #fff;
padding-left: 20px!important;
padding-right: 20px!important;
box-shadow: 0 8px 10px rgba(0, 0, 0, 0.1);
}
button:hover{
background-color: #1A314B!important;
animation: pulseAnimation 2s ease-in-out infinite!important;
}

@keyframes pulseAnimation {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
@keyframes flutuar {
0% { transform: translateY(0); }
50% { transform: translateY(-20px); }
100% { transform: translateY(0); }
}
@keyframes pulse {
0% { transform: scale(1); }
50% { transform: scale(1.1); }
100% { transform: scale(1); }
}
</style>
<script>

export default {
  name: "login",
  data() {
    return {
      email: "",
      senha: "",
      emailValid: true,
      imageSrc: "C.png",
    };
  },
  methods: {
     logar() {
    

    },

    updateImage(){

      if(this.senha){
          this.imageSrc = "public/open.png"
      }else{
        this.imageSrc = "public/C.png"
      }

      if(this.$refs.senha1.type == "text"){
        this.imageSrc = "FundoCipa.png"
      }

    },
    cadastre() {
      this.$router.push("cadastro");
    },
    recuperar() {
      return this.$router.push("/email");
    },
    checkEmail(){
      if (!this.email.endsWith('discente.ifpe.edu.br')) {
        this.emailIsValid = false;
      } else {
        this.emailIsValid = true;
      }
    }
  },
};
</script>
