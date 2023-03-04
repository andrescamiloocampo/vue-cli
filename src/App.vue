<template>
  <main id="app">
        <nav>
            <h1>Ejercicios JavaScript</h1>
        </nav>

        <section class="sintax">
            <h3 id="titulo">1.JS Syntax</h3>
            <article id="sa1">
                <h4>Mensaje por consola</h4>
                <button @click="mensajeConsola()">
                    <h4>Click aquí</h4>
                </button>
            </article>

            <article id="sa2">
                <h4>Declaracion de variables y constantes</h4>
                <input type="text" placeholder="VAR-GLOBAL" v-model="variable">
                <input type="text" placeholder="CONST-CONSTANTE" readonly>
                <input type="text" placeholder="LET-BLOQUE" v-model="bloque">
                <br><br>
                <h4>var {{variable}}</h4>
                <h4>const {{constante}}</h4>
                <h4>let {{bloque}}</h4>
            </article>

            <article id="sa3">
                <h4>Suma</h4>
                <input type="number" v-model="x">+<input type="number" v-model="y">
                <h4 id="res">= {{x+y}}</h4>
            </article>
        </section>


        <section class="datos">
            <h3>2.Tipos de datos</h3>

            <article id="at1">
                <input type="number" step="0.1" placeholder="Ingrese un numero" v-model="num">
                <button @click="tiposDeDatos(num)">
                    <h4>Mostrar tipo de dato</h4>
                </button><br>

                <input type="text" placeholder="Ingrese texto" v-model="text">
                <button @click="tiposDeDatos(text)">
                    <h4>Mostrar tipo de dato</h4>
                </button><br>

                <label for="check" id="cb">Checkbox</label>
                <input type="checkbox" name="" id="check" @click="tiposDeDatos(booleano)" v-model="booleano">
            </article>

            <article id="at2">
                <h4 id="tl">Lista</h4>
                <ul>
                    <li v-for="fruta in fruits" v-bind:key="fruta">
                        {{fruta}}
                    </li>
                </ul>
                <br>
                <button @click="tiposDeDatos(fruits)">
                    <h4>Mostrar tipo de dato</h4>
                </button>
                <h4 v-if="tipo!=''">{{tipo}}</h4>
            </article>
        </section>

        <section class="numeros">
            <h3>3.Numeros</h3>
            <article id="an">
                <section id="subN">
                    <input type="number" step="0.1" placeholder="Ingrese un numero" v-model="num1">
                    <input type="number" step="0.1" placeholder="Parte imaginaria" v-model="im">
                </section>

                <section id="subN1">
                    <button @click="cambiarTipo(num1,0)">float</button>
                    <button @click="cambiarTipo(num1,1)">int</button>
                    <button @click="pasarComplejo(num1,im)">complex</button>
                </section>
            </article>
        </section>

        <section class="cadenas">
            <h3 id="titleC">4.Strings</h3>

            <article id="cd1">
                <h4 id="td1">Medir una cadena</h4>
                <input type="text" placeholder="Ingrese texto" id="cad" v-model="cadena" @change="medir">
                <h2 id="cad1">{{cadena}}</h2>
                <h3 id="med">Medida: {{medida}} </h3>
            </article>


            <article id="cd2">
                <h4>Acceso a caracteres</h4>
                <h4>{{texto}}</h4>
                <input type="number" v-model="x">
                <button @click="caracter = texto[x]">Mostrar carácter</button>
                <h1>{{caracter}}</h1>

                <h4>Rango de caracteres</h4>

                <section id="cd22">
                    <input type="text" style="width: 35px !important; margin-left: 10px; border-radius: 5px;" v-model="inf">
                    <input type="text" style="width: 35px !important; margin-left: 10px; border-radius: 5px;" v-model="sup">
                </section>

                <h3>{{texto.substring(inf,sup)}}</h3>
            </article>

            <section id="cd3">
                <h4>Eliminar espacios</h4>
                <h4>{{texto1}}</h4>
                <button id="botonq" @click="quitarEspacios">Quitar espacios</button>

                <h4 style="margin-top: 25px;">Mayusculas y minusculas</h4>
                <h4>{{texto2}}</h4>

                <article id="cd3-1">
                    <button @click="letras(0)">MAYÚSCULAS</button>
                    <button @click="letras(1)">minúsculas</button>
                </article>
            </section>


            <section id="cd4">
                <h4 style="margin-top: 25px;">Cambiar letras</h4>
                <h4>{{texto2}}</h4>

                <article id="cd4-1">
                    <input type="text" placeholder="Ingrese una letra a reemplazar" v-model="caracter1">
                    <input type="text" placeholder="Ingrese la nueva letra" v-model="caracter2">
                </article>
                <button @click="reemplazar">Reemplazar</button>

                <h4 style="margin-top: 25px;">Template strings</h4>
                <input id="nom" style="margin-top: 10px; " type="text" placeholder="Ingrese su nombre" v-model="name">
                <h4 style="margin-bottom: 20px; margin-top: 20px;">Hello my name is: {{name}}</h4>
                
            </section>
        </section>


        <section id="bo">
            <h3>5.Booleans</h3>
            <article id="bo1">
                    <input type="text" placeholder="Ingrese una validacion" v-model="exp">
                    <button @click="interpretar(exp)">Validar expresion</button>
                    <h4>{{validar}}</h4>
            </article>
        </section>


        <section id="op">
            <h3 style="margin-top: 40px;">6.Operators</h3>
            
                <article id="op1">
                    <br>
                    <h4 style="margin-bottom: 10px;">Operadores aritmeticos</h4>

                    <section class="op1-1">
                        <input type="number" step="0.1" id="inputS" class="inputS"> + <input type="number" step="0.1" id="inputS1" class="inputS1"> = <p>
                            {{resultados[0]}}</p>
                        </section>
                        <button class="bs" @click="operaciones(1)">sumar</button><br>
    
                    <section class="op1-1" style="margin-top: 10px;">
                        <input type="number" step="0.1" id="inputR" class="inputS"> - <input type="number" step="0.1" id="inputR1" class="inputS1"> = <p>
                            {{resultados[1]}}</p>
                    </section>
                    <button class="bs" @click="operaciones(2)">restar</button><br>

                    <section class="op1-1" style="margin-top: 10px;">
                        <input type="number" step="0.1" id="inputM" class="inputS"> * <input type="number" step="0.1" id="inputM1" class="inputS1"> = <p>
                            {{resultados[2]}}</p>
                    </section>
                    <button class="bs" @click="operaciones(3)">multiplicar</button><br>
    
                    <section class="op1-1" style="margin-top: 10px;">
                        <input type="number" step="0.1" id="inputD" class="inputS"> / <input type="number" step="0.1" id="inputD1" class="inputS1"> = <p>
                            {{resultados[3]}}</p>
                    </section>
                    <button class="bs" @click="operaciones(4)">dividir</button><br>
                </article>
    
                
                <article id="op2">
                    <h4 style="margin-top: 3%;">Operador "in" en JavaScript</h4>
                    <ul>
                        <li v-for="fruta in fruits" v-bind:key="fruta">
                            {{fruta}}
                        </li>
                    </ul>
                    <input type="text" id="fruitInput" placeholder="Ingrese una fruta">
                    <button @click="incluye">Buscar fruta</button>
                </article>
        
        </section>

        <footer></footer>

    </main>
</template>

<script>


export default {
  name: 'App',
  components: {
  },
    data(){
        return{
            medida:0,
            variable:'',
            bloque:'',
            constante:'constante=5',
            x:0,
            y:0,
            num:0,
            num1:0,
            im:'',
            booleano:false,
            text:'',
            tipo:'',
            fruits:['Apple','Banana','Cherry'],
            cadena:'...',
            texto:'Hello world',
            texto1:'    Hello world     ',
            texto2:'Hello world',
            caracter:'',
            caracter1:'',
            caracter2:'',
            inf:0,
            sup:0,
            name:'',
            validar:false,
            exp:'',
            resultados:[]
        }
    },
    computed(){
        this.medir()
    },
    watch:{
    
    },
    methods:{
        mensajeConsola(){
            console.log("Hello world")
        },
        //Asi se hace un comentario 
        tiposDeDatos(x){
            this.tipo = typeof(x)
        },
        cambiarTipo(x,op){
            switch(op){
                case 0:
                   x = parseFloat(x)
                   console.log(x,typeof(x))
                break;

                case 1:
                    x = parseInt(x)
                    console.log(x,typeof(x))
                break;
                
                case 2:
                    this.pasarComplejo(x,this.im)
                break;
            }
        },
        pasarComplejo(x,i){
            if(i==''){
              alert("Ingrese la parte imaginaria")
            }else{
                let complejo = (function(real,imag){
                    return{real:real,imag:imag}
                })(x,i)
                console.log(complejo.real, '+' ,complejo.imag, 'i')
            }
        },
        medir(){
            this.medida = this.cadena.length
        },
        quitarEspacios(){
            console.log(this.texto1)
            this.texto1 = this.texto1.trim()
            console.log(this.texto1)
        },
        letras(x){
            switch(x){
                case 0:{
                    this.texto2 = this.texto2.toUpperCase()
                    console.log(this.texto2)
                    break;
                }
                case 1:{
                    this.texto2 = this.texto2.toLowerCase()
                    console.log(this.texto2)
                    break;
                }
            }
        },
        reemplazar(){
            this.texto2 = this.texto2.replace(this.caracter1,this.caracter2)
        },
        interpretar(exp){
            this.validar = eval(exp)
        },
        operaciones(x){
            switch(x){
                case 1:{
                    const input1 = document.getElementById('inputS')
                    const input2 = document.getElementById('inputS1')
                    this.resultados[0] = parseFloat(input1.value) + parseFloat(input2.value)
                    break;
                }
                case 2:{
                    const input1 = document.getElementById('inputR')
                    const input2 = document.getElementById('inputR1')
                    this.resultados[1] = parseFloat(input1.value) - parseFloat(input2.value)
                    break;
                }
                case 3:{
                    const input1 = document.getElementById('inputM')
                    const input2 = document.getElementById('inputM1')
                    this.resultados[2] = parseFloat(input1.value) * parseFloat(input2.value)
                    break;
                }
                case 4:{
                    const input1 = document.getElementById('inputD')
                    const input2 = document.getElementById('inputD1')
                    this.resultados[3] = parseFloat(input1.value) / parseFloat(input2.value)
                    break;
                }
            }
        },
        incluye(){
            const fruta = document.getElementById('fruitInput')
            if(this.fruits.includes(fruta.value))
               alert("La fruta se encuentra en la lista") 
            else
               alert("La fruta no se encuentra en la lista")
        }
    }
}
</script>

<style>
*{
    margin:0%;
    padding: 0%;
}

html,body{
    width: 100%;
    height: 100%;
    font-family: sans-serif;
}

main{
    width: 100%;
    height: 100%;
}

footer{
    width: 100%;
    height: 10%;
    background-color: #282A35;
    margin-top: 5%;
}
section{
    text-align: center;
}
section h1{
    margin-top: 50px;
}
main h3{
    margin-left: 50px;
    margin-top: 20px;
    margin-bottom: 20px;
}

main ul{
    margin-left: 100px;
}

main li{
    margin-top: 10px;
}

.listaN input{
    margin-top: 15px;
    margin-bottom: 15px;
}

#cad{
    margin-top: 15px;
}

#cad1{
    margin-top: 5px;
    margin-left: 25px;
}

#med{
    margin-top: 5px;
}

nav{
    width: 100%;
    height: 10%;
    background-color: #282A35;
    color: white;
    display: flex;
    justify-content:center;
    align-items:center;
}

.sintax{
    background-color: #D9EEE1;
    width: 50%;
    margin-left: 25%;
    margin-top: 5%;
    border-radius: 5px;
}

#titulo{
    text-align: left;
    color: black;
    padding-top:2%;
    width: fit-content;
}

#sa1{
    display: flex;
    width: 40%;
    margin-left: 30%;
    height: fit-content;
    padding: 25px;
    flex-direction: column;
    border-radius: 5px;
    background-color: #282A35;
    color: white;
}

#sa2{
    display: flex;
    flex-direction: column;
    width: 48%;
    height: fit-content;
    margin-top: 5%;
    margin-left: 30%;
    background-color:#282A35;
    border-radius: 5px;
    color: white;
}

#sa2 input{
    margin-top: 10px;
    width: 90%;
    margin-left: 5%;
    padding-top: 2%;
    padding-bottom: 2%;
    border: none;
    border-radius: 15px;
}

#sa2 h4:first-of-type{
    margin-top: 20px;
    margin-bottom: 15px;
    text-align: center;
}

#sa2 h4{
    text-align: left;
    margin-left: 15px;
    margin-bottom: 20px;
}

#sa1 button{
    width: 90%;
    margin-top: 5%;
    margin-left: 5%;
    padding-left: 20%;
    padding-right: 20%;
    padding-top: 3%;
    padding-bottom: 3%;
    cursor: pointer;
    background-color:#04AA6D;
    color: white;
    font-size: 16px;
    border:none;
    border-radius: 30px;
}

#sa1 button:hover{
    background-color: #06ea96;
}

#sa3{
    display: flex;
    width: 48%;
    color: white;
    height: fit-content;
    background-color:#282A35;
    flex-direction: row;
    margin-top: 40px;
    margin-left: 30%;
    align-items: center;
    justify-content: space-between;
    border-radius: 5px;
}

#sa3 input{
    width: 20%;
    height: 10%;
    border: none;
    border-radius: 15px;
    padding: 1%;
}

#sa3 h4{
    margin-top: 15px;
    margin-bottom: 15px;
    margin-left: 30px;
}

#sa3 #res{
    margin-right: 30px;
}

.datos{
    display: flex;
    flex-direction: column;
    margin-top: 5%;
    background-color: #D9EEE1;
    width: 50%;
    margin-left: 25%;
    border-radius: 5px;
}

.datos h3{
    text-align: left;
}

#at1{
    display: flex;
    flex-direction: column;
    background-color: #282A35;
    color: white;
    width: 60%;
    margin-left: 20%;
    border-radius: 5px;
}

#at1 input:first-of-type{
    margin-top: 20px;
}

#at1 input{
    width: 80%;
    margin-left: 10%;
    border: none;
    border-radius: 15px;
    padding-top: 2%;
    padding-bottom: 2%;
}

.datos button{
    width: 81%;
    margin-left: 10%;
    margin-top: 3%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border:none;
    background-color: #04AA6D;
    color: white;
    cursor: pointer;
}

.datos button:hover{
    background-color: #06ea96;
}

#check{
    margin-bottom: 15px;
}

#at2{
    display: flex;
    flex-direction: column;
    margin-top: 15px;
    background-color: #282A35;
    width: 60%;
    margin-left: 20%;
    border-radius: 5px;
    color: white;
    text-align: center;
    margin-bottom: 20px;
}

#at2 ul{
    margin-left: -300px;
}

#tl{
    margin-top: 20px;
}

#at2 button{
    margin-bottom: 10px;
}

.numeros{
    width: 50%;
    height: fit-content;
    background-color:#D9EEE1;
    display: flex;
    flex-direction: column;
    margin-left: 25%;
    margin-top: 60px;
    border-radius: 5px;
}

.numeros h3{
    text-align: left;
}

#an{
    background-color: #282A35;
    display: flex;
    flex-direction: column;
    width: 60%;
    margin-left: 20%;
    margin-bottom: 5%;
    border-radius: 5px;
}

#subN{
    display: flex;
    justify-content: space-between;
}

#subN input{
    margin-top: 10px;
    padding-top: 2%;
    padding-bottom: 2%;
    border: none;
    border-radius: 15px;
    margin-bottom: 20px;
}

#subN input:first-child{
    margin-left: 20px;
}

#subN input:last-child{
    margin-right: 20px;
}

#subN1{
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
}

#subN1 button{
    margin-bottom: 8px;
    width: 20%;
    border-radius: 15px;
    border: none;
    background-color: #04AA6D;
    color: white;
}

#subN1 button:hover{
    background-color: #06ea96;
}

@media (max-width:1220px) {
    #subN{
        flex-direction: column;
        justify-content: center;
    }
    #subN input{
        margin-left: 0px;
        margin-right: 0px;
    }
}

.cadenas{
    background-color: #D9EEE1;
    width: 50%;
    margin-left: 25%;
    margin-top: 5%;
    border-radius: 5px;
}

.cadenas #titleC{
    text-align: left;
    width: fit-content;
    padding-top: 20px;
}

#cd1{
    background-color: #282A35;
    width: 60%;
    margin-left: 20%;
    color: white;
    border-radius: 5px;
    justify-content: center;
}

#td1{
    padding-top: 15px;
    padding-bottom: 10px;
}

#cd1 input{
    padding-top: 2%;
    padding-bottom: 2%;
    border: none;
    width: 80%;
    border-radius: 15px;
}

#cad1{
    margin-left: 45%;
    margin-bottom: 5%;
    width: fit-content;
}

#med{
    margin-left: 42%;
    padding-bottom: 10px;
    width: fit-content;
    height: fit-content;
}

#cd2{
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    background-color: #282A35;
    color: white;
    margin-top: 5%;
    width: 60%;
    margin-left: 20%;
    border-radius: 5px;
}

#cd2 h4{
    margin-top: 10px;
    margin-bottom: 20px;
}

#cd2 input{
    width: 80%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border: none;
    margin-left: 10%;
    margin-bottom: 5%;
}

#cd2 button{
    width: 80%;
    margin-left: 10%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    background-color: #04AA6D;
    border: none;
    color: white;
    cursor: pointer;
}

#cd2 button:hover{
    background-color: #06ea96;
}

#cd2 h3{
    margin-left: 3%;
}

#cd3{
    display: flex;
    flex-direction: column;
    background-color: #282A35;
    color: white;
    margin-top: 5%;
    margin-left: 20%;
    border-radius: 5px;
    width: 60%;
    justify-content: center;
    text-align: center;
}

#cd3 h4{
    margin-top: 15px;
    margin-bottom: 15px;
}

#botonq{
    background-color: #04AA6D;
    border: none;
    padding-top: 2%;
    padding-bottom: 2%;
    width: 80%;
    margin-left: 10%;
    color: white;
    border-radius: 15px;
    cursor: pointer;
}

#botonq:hover{
    background-color: #06ea96;
}

#cd3-1{
    display: flex;
    justify-content: space-evenly;
}

#cd3-1 button{
    width: 40%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border: none;
    margin-bottom: 10px;
    color: white;
    background-color: #04AA6D;
    cursor:pointer;
}

#cd3-1 button:hover{
    background-color: #06ea96;
}

#cd4{
    display: flex;
    flex-direction: column;
    margin-top: 5%;
    background-color: #282A35;
    justify-content: center;
    width: 60%;
    height: fit-content;
    margin-left: 20%;
    border-radius: 5px;
    color: white;
}

#cd4 h4{
    margin-top: 10px;
    margin-bottom: 15px;
}

#cd4 button{
    width: 88%;
    margin-left: 6%;
    margin-top: 5px;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border: none;
    background-color: #04AA6D;
    cursor: pointer;
    color: white;
}

#cd4 button:hover{
    background-color: #06ea96;
}

#cd4-1{
    display: flex;
    justify-content: space-evenly;
}

#cd4-1 input{
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border: none;
    margin-bottom: 10px;
}

#nom{
    border-radius: 15px;
    padding-top: 2%;
    padding-bottom: 2%;
    width: 80%;
    margin-left: 10%;
    border: none;
}

#bo{
    display: flex;
    flex-direction: column;
    background-color: #D9EEE1;
    width: 50%;
    margin-left: 25%;
    margin-top: 5%;
    border-radius: 5px;
}

#bo h3:first-child{
    text-align: left;
}

#bo1{
    display: flex;
    flex-direction: column;
    background-color: #282A35;
    color: white;
    width: 60%;
    margin-left: 20%;
    border-radius: 5px;
    margin-bottom: 5%;
}

#bo1 input{
    margin-top: 20px;
    margin-bottom: 20px;
    width: 80%;
    margin-left: 10%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border: none;
}

#bo1 h4{
    margin-bottom: 20px;
}

#bo1 button{
    width: 80%;
    margin-left: 10%;
    padding-bottom: 2%;
    padding-top: 2%;
    border-radius: 15px;
    border: none;
    background-color: #04AA6D;
    color: white;
    cursor:pointer;
    margin-bottom: 20px;
}

#bo1 button:hover{
    background-color: #06ea96;
}

#op{
    background-color: #D9EEE1;
    width: 50%;
    margin-left: 25%;
    margin-top: 5%;
    border-radius: 5px;
}

#op h3{
    text-align: left;
    padding-top: 3%;
}

#op1{
    background-color: #282A35;
    color: white;
    width: 60%;
    margin-left: 20%;
    border-radius: 5px;
}

.op1-1{
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
}

.inputS{
    width: 30%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius:15px;
    border:none;
}

.inputS1{
    width: 30%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius:15px;
    border: none;
}

.bs{
    width: 75%;
    margin-top: 5px;
    margin-bottom: 5px;
    margin-left: -50px;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    cursor: pointer;
    color: white;
    background-color: #04AA6D;
    border: none;
}

.bs:hover{
    background-color: #06ea96;
}

#op2{
    background-color: #282A35;
    width: 60%;
    margin-left: 20%;
    margin-top: 5%;
    border-radius: 5px;
    color: white;
    display: flex;
    flex-direction: column;
}

#op2 input{
    width: 80%;
    margin-left: 10%;
    padding-top: 2%;
    padding-bottom: 2%;
    border-radius: 15px;
    border:none;
    margin-bottom: 2%;
}

#op2 ul{
    list-style: none;
    margin-right: 90%;
    margin-bottom: 5%;
}

#op2 button{
    width: 80%;
    margin-left: 10%;
    padding-top: 2%;
    padding-bottom: 2%;
    margin-bottom: 2%;
    border-radius: 15px;
    border: none;
    background-color: #04AA6D;
    color: white;
    cursor: pointer;
}

#op2 button:hover{
    background-color: #06ea96;
}
</style>
