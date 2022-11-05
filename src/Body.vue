<template>
    <div>
        <form class="input-group p-3" v-on:submit="onSubmit">
            <input type="text" @keyup="myInput" :value="myText" class="form-control">
            <button class="btn btn-success">
                <span :style="{fontWeight:'bolder'}">+ Add</span>
            </button>
        </form>
    </div>
</template>

<script>
    export default{
        data : function(){
            return{
                myArray : this.itemArray,
                myText : this.textStrng
            }
        },
        methods : {
            onSubmit : function(event){
                event.preventDefault();
                this.myArray.push(this.myText);    
                this.myText = "";
                this.$emit("AllItem",this.myArray);
            },
            myInput : function(event){
                var available = event.target.value;
                this.myText = available;
                return this.myText;
            }
        },
        props : ["itemArray","textStrng"],
        
    }
</script>