<template>
    <div class="card-footer p-0">
        <ul class="list-group" >
            <li v-for="value of args" class="list-group-item rounded-0 d-flex align-items-center justify-content-between">
                <div :style="{maxWidth:'270px'}">
                    <span :style="{maxWidth:'270px'}">
                        {{value}}
                    </span>
                </div>
                <div>
                    <button @click="deleteObject" v-bind:style="{fontWeight:'bold'}" class="btn btn-danger" >
                        - Delete
                    </button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data : function(){
            return{
                args : this.kontrolDot
            }
        },

        methods : {
            deleteObject : function(event){
                console.log(event.target.parentNode.parentNode.remove())
            }
        },

        props : ["kontrolDot"]
    }
</script>