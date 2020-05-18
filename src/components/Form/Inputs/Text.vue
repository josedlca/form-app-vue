<template>
    <input 
        type="text"
        :id="identity"
        :name="name"
        :value="value"
        :maxlength="maxlength"
        :placeholder="placeholder"
        :autocomplete="autocomplete"
        v-on="inputListeners"
    >
</template>

<script>
    export default {
        props:{
            group:{
                type: String,
                required: false
            },
            name: {
                type:String,
                required:true
            },
            id:{
                type:String,
                required:false
            },
            value:{
                default:''
            },
            currentValue:{
                default:''
            },
            placeholder:{
                type:String,
                required:false
            },
            maxlength:{
                type:String,
                required: false
            },
            autocomplete:{
                type:String,
                required: false
            }
        },
        data(){
            return{
                identity: this.id ? this.id : this.name,
            }
        },
        computed:{
            inputListeners(){
                return Object.assign({}, this.$listeners,{
                    input: event =>{
                        this.emit(event.target.value);
                    }
                })
            }
        },
        mounted(){
            this.emit(this.currentValue);        
        },
        methods:{
            emit(value){
                this.$emit('input', value);
            }
        }
    }
</script>