<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale : theme==='sale' }" >
            <slot></slot>
        <div class="actions">
            <slot name="links"></slot>
        </div>
        </div>
    </div>
</template>
<script>
export default {
    props:[ 'theme' ],
    methods:{
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>


<style >
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
   

}
.backdrop{
    top: 0;
    position: fixed;
    background: rgba(128, 128, 128, 0.315);
    width: 100%;
    height: 100%;
}
.modal h1{
    color: rgb(10, 9, 9);
    border: none;
    padding: 0;
}
.modal p{
    font-style: normal;
    color: rgb(16, 106, 240);
}
.modal.sale{
    background: rgb(211, 165, 165);
    border-radius: 15px 50px 30px;
    padding: 10px;
  box-shadow: 5px 10px #888888;
    

}
.modal.sale h1{
    color: white;
}
.modal .actions{
text-align: center;
margin: 30px 0 10px 0;

}
.modal .actions a{
color: rgb(238, 92, 24);
padding: 8px;
border:1px solid #eee;
border-radius: 4px;
text-decoration: none;
margin: 10px;
}
.modal.sale .actions{
    color: white;
}
.modal.sale .actions a{
    color: white;
}
</style>