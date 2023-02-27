<script>
import { ref } from 'vue'
export default {
  setup() {
    const query = ref('')
    const submitForm = () => {
      console.log('submitting form. Value searched =',query.value)} 
      
      const reset = (evt) => {
      query.value = '' // clears the query
    }

    return {
      query,
      submitForm,
      reset,
    }
  },
}



</script>



<template>
  <div>
    <h2>Filter LearnVue Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <br>
    <button class="btn" 
    :disabled="query.length==0"
    @click="submitForm">submit

    </button>  
   <br>
   <button class ="btn" @click="reset">Reset</button>
   <br>
    <div class="read-the-docs">
      <a href="https://v3.vuejs.org/guide/introduction.html" target="_blank">Read the Docs</a>
    </div>
    <br>
    <br>
   {{ query }}
  </div>
</template>

<style>
  .read-the-docs {
    text-align: center;
}
  .btn{
      margin-top: 1rem;
    }
  
  </style>

