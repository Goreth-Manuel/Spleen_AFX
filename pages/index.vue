<template>
    <div class="min-h-screen bg-indigo-950 flex items-center justify-between px-50"
    :style="{
      background: 'linear-gradient(235.64deg, #4831A2 -1.78%, rgba(13, 7, 39, 0.9) 52.42%, #1F1153 134.35%)',
    }"
   >
      
        <div class="w-3xl h-[890px] ml-8 px-5 flex flex-col justify-center">
          <div class="mb-10">
            <div class="flex items-center gap-2 mb-6">
              <img src="/S.svg" alt="Letra S"  class="w-[30px] pb-5"/>

              <span class="text-white text-[28px] pb-5">Spleen AFX</span>
            </div>
            
            <h1 class="text-white text-[38px] font-bold mb-2">Olá, Seja bem-vindo</h1>
            <p class="text-gray-300 text-[18px] pb-6">Aproveite da melhor coleção de música à sua escolha, entre agora</p>
          </div>
          
          <form @submit.prevent="handleLogin" class="space-y-4">
            <div>
              <label for="email" class="block text-gray-300 text-sl mb-1">Email Address</label>
              <input 
                id="email" 
                v-model="email" 
                type="email" 
                class="w-full p-5 rounded-md bg-transparent border border-white text-white focus:outline-none focus:ring-2 focus:ring-yellow-300"
                placeholder="your.email@example.com"
              />
            </div>
            
            <div>
              <label for="password" class="block text-gray-300 text-sl mb-1">Password</label>
              <div class="relative">
                <input 
                  id="password" 
                  v-model="password" 
                  :type="showPassword ? 'text' : 'password'" 
                  class="w-full p-5 rounded-md bg-transparent border border-white text-white focus:outline-none focus:ring-2 focus:ring-yellow-300"
                  placeholder="8+ caracteres necessários"
                />
                <button 
                  type="button" 
                  @click="showPassword = !showPassword" 
                  class="p-4 absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                >
                  <span v-if="showPassword">👁️</span>
                  
                  <span v-else>
                    <img src="/eyes.svg" alt="Olhos abertos" />
                  </span>
                </button>
              </div>
            </div>
            
            <div class="flex justify-between items-center">
              <div class="flex items-center">
                <input 
                  id="remember" 
                  v-model="rememberMe" 
                  type="checkbox" 
                  class="h-5 w-8 rounded  border-indigo-700 text-yellow-300 focus:ring-yellow-300"
                />
                <label for="remember" class="ml-2 text-sl text-gray-300">Mantenha-me Logado</label>
              </div>
              <a href="#" class="text-yellow-300 text-sl hover:underline">Forgot Password?</a>
            </div>
            
            <div class="flex items-center">
              <input 
                id="terms" 
                v-model="acceptTerms" 
                type="checkbox" 
                class="h-5 w-8 rounded border-indigo-700 text-yellow-300 focus:ring-yellow-300"
                required
              />
              <label for="terms" class="ml-2 text-sl text-gray-300">
                Eu aceito os <a href="#" class="text-yellow-300 hover:underline">Termos de uso</a> e <a href="#" class="text-yellow-300 hover:underline">Subscrições</a>
              </label>
            </div>
            
            <button 
              type="submit" 
              class="w-full bg-yellow-300 hover:bg-yellow-400 text-[#6046C5] text-[18px] font-medium py-4 px-4 rounded-md transition duration-200"
            >
              Iniciar Sessão
            </button>
          </form>
        </div>

          <img src="/person-with-headphones.svg" alt="Pessoa com fones de ouvido" class="w-[760px] h-[900px] ml-[58px] "/>
      

       
      </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue'
  
  const email = ref('')
  const password = ref('')
  const rememberMe = ref(false)
  const acceptTerms = ref(false)
  const showPassword = ref(false)
  
  const handleLogin = () => {

    if (!email.value || !password.value) {
      alert('Por favor, preencha todos os campos obrigatórios')
      return
    }
    
    if (!acceptTerms.value) {
      alert('Você precisa aceitar os termos de uso')
      return
    }
    
    console.log('Login com:', {
      email: email.value,
      password: password.value,
      rememberMe: rememberMe.value
    })
    
    alert('Login bem-sucedido! Redirecionando...')
  }
  </script>