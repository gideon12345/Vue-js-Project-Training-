<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale:theme === 'sale'}">
          <slot>Default Content</slot> 
          <div class="actions">
            <slot name="links"></slot>
          </div> 
        </div>

    </div>
    
</template>

<script>
export default{
    props:['header',"text"],
    methods:{
        closeModal(){
            this.$emit('close')

        }
    }
}
</script>


 

<style scoped>
.modal{
    width: 400px;
    padding: 20px;
    margin:100px auto;
    background: crimson;
    border-radius:10px;
}
.backdrop{
    top:0;
    position: fixed;
    backdrop-filter: rgb(0,0,0.5);
    width: 100%;
    height: 100%;
}
.modal .sale{
    background: crimson;
    color:white;


}

.modal .actions{
    text-align: center;
    margin: 30p 0 10px 0;
    color: #333;

}

.modal .actions a{
    color :#333;
    padding :8px;
    border:1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin:10px ;
}

</style>