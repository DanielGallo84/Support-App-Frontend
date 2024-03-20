<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const usuario = ref('');
const contraseña = ref('');
//const recordarContraseña = ref(false);
const router = useRouter();

const enviarFormulario = async () => {
  try {
    const response = await fetch('http://localhost:8080/api/usuarios/login', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({ usuario: usuario.value, contraseña: contraseña.value }),
    });

    if (response.ok) {
      console.log('Inicio de sesión completado');
      
      router.push('/about');
    } else {
      const errorMessage = await response.text();
      console.error('Credenciales inválidas:', errorMessage);
      
      alert('Credenciales incorrectas');
    }
  } catch (error) {
    console.error('Error de red:', error);
  }
};
</script>

<template>
  <form class="login" @submit.prevent="enviarFormulario">

    <h1>Bienvenido</h1>

    <label for="usuario">Usuario</label>
    <input type="text" id="usuario" name="usuario" v-model="usuario" required>

    <label for="contraseña">Contraseña</label>
    <input type="password" id="contraseña" name="contraseña" v-model="contraseña" required>

    <!-- <div class="rememberPassword">
      <input type="checkbox" id="recordar" name="recordar" v-model="recordarContraseña">
      <label for="recordar">Recordar contraseña</label>
    </div> -->

    <button type="submit">ACCEDER</button>

  </form>
</template>
  
  <style lang="scss" scoped>

    @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
  
  .login {
    height: 80%;
    background-color: rgba(58, 39, 173, 0.28);
    max-width: 300px;
    margin: 20px auto;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    color:rgba(58, 39, 173, 1);
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-weight:bold;

    h1 {
        text-align: center;
        font-size: 2rem;
        margin-bottom: 15px;
        
    }
  }
  
  .rememberPassword {
    display: flex;
    align-items: center;
    margin-bottom: 16px;
    margin-top: 10px;
    margin-right: 105px;
  }
  
  .rememberPassword input[type="checkbox"] {
    transform: scale(0.9);
    margin-right: 8px;
  }
  
  .rememberPassword label {
    white-space: nowrap; 
  }
  
  label {
    display: block;
    margin-bottom: 5px;
    text-align: center;
  }
  
  input {
    width: 100%;
    padding: 8px;
    margin-bottom: 8px;
    box-sizing: border-box;
    border-radius: 10px;
  }
  
  button {
    background-color: rgba(143, 253, 194, 0.72);
    color:rgba(58, 39, 173, 1);
    padding: 10px;
    border: none;
    border-radius: 10px;
    cursor: pointer;

    margin-left: 90px;
  }
  </style>