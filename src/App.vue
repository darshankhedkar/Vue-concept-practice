<template>
<h1>hello bhai log kya kar rahe ho tum sab..!! <br>lets try this out</h1>
 <teleport to="#modal" v-if="showModal">
   <Modal theme ="sale" @close="toggleModal">
     
     <template v-slot:links>
       <a href="#">Signup</a>
        <a href="#">Login</a>
     </template>

     <h1>This is h1 tag for slot</h1>
     <p>this is paragraph tag</p>
    
   </Modal>
   
 </teleport>
<!-- second modal -->
 <teleport to="#modal" v-if="showModalTwo">
   <Modal  theme="sale" @close="toggleModalTwo">

     <h1>This is slot</h1>
     <p>this is Content </p>
    
   </Modal>
   
  </teleport >
<button @click="toggleModal">open modal</button>
<button @click="toggleModalTwo">open modalTwo</button>
 

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data(){
    return {
      title:'this is the title:)',
      header:'this is header props',
      text:'this is text element',
      showModal:false,
      showModalTwo:false,
    }
  },
  methods:{
    toggleModal(){
      this.showModal=!this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo=!this.showModalTwo
    }
  }

}
</script>

<style >
#app,#modal {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #55a0ecb7;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid blanchedalmond;
  padding-bottom: 10px;
}
</style>
