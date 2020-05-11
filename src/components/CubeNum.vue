<template>
    <div>
        <div class="question">
        <label>Enter a number : </label>
        <input v-model.lazy="number" v-on:keyup.enter="checkNum" type="text"/>
        <button v-on:click="checkNum">CUBE</button>
        </div>

        <div v-show="validNum" class="answer">
            <div class="cube-text">CUBE : </div>
            <div class="cube">{{cubeCalc}}</div>
        </div>
        
    </div>
</template>



<script>
export default {
    name : "CubeNum",
    data(){
        return{
            number : null,
            validNum : false
        }
    },
    methods:{
        checkNum : function(){
            if(!isNaN(this.number))
                this.validNum = true
            else{
                this.validNum = false
                this.number = null
                alert("Enter a valid number")

            }
            
        }
    },
    computed : {
       
        cubeCalc : function(){
           
               

                return Number(this.number)%1==0 ? Math.pow(Number(this.number) , 3) : Math.pow(Number(this.number) , 3).toFixed(3)
            
            
        }
    }
    
}
</script>

<style scoped>
input[type=number]::-webkit-inner-spin-button, 
input[type=number]::-webkit-outer-spin-button { 
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    margin: 0; 
}
.question{
    display: flex;
    margin-left: 25%;
}
label{
    font-family: 'Trebuchet MS' ;
    font-size: 35px;
   
}
input{
    width: 15%;
    height: 50px;
    border: 2px solid rgb(26, 128, 35);
    border-radius: 10px;
    font-size: 30px;
    margin-left: 1%;
}
input:focus, button:focus, select:focus{
        outline: none;
    }

button{
    margin-left: 2%;
    height: 50px;
    width: 100px;
    background-color: rgb(255, 72, 0);
    color: #fff;
    border : none;
    border-radius: 15px;
    font-size: 20px;
}
button:hover{
    cursor: pointer;
}
.answer{
    display: flex;
    margin-top: 10%;
    font-family: 'Trebuchet MS' ;
    font-size: 40px;
}
.cube-text{
    margin-left: 40%;
   
    color: rgb(12, 12, 105);
    
}
.cube{
    color: rgb(65, 107, 23);
    margin-left: 2%;
}

</style>