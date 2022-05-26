<template>
    <div class="h-screen bg-emerald-200 flex justify-center py-16">
        <div class="w-1/3">     
            <div class="bg-emerald-50 p-3 shadow-2xl text-xl text-right border-2 rounded-t-lg">
                <div class="font-semiblod text-gray-700 h-6">{{ getOperation }}</div>
                <div class="font-bold text-3x1 text-gray-900 my-2">{{ getResult }}</div>
            </div>
          
          <div class="grid grid-cols-4 grid-rows-5 shadow-2xl rounded-lg bg-emerald-200">
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-500 col-span-2 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="clickAC()">AC</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-500 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="clickDEL()">DEL</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-700 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('/')">/</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('7')">7</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('8')">8</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('9')">9</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-700 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('*')">*</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('4')">4</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('5')">5</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('6')">6</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-700 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('+')">+</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('1')">1</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('2')">2</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('3')">3</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-700 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-emerald-100" @click="click('-')">-</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-500 border-2 border-emerald-300 transition ease-in-out delay-250 rounded-bl-lg hover:bg-sky-100" @click="click('.')">.</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-400 border-2 border-emerald-300 transition ease-in-out delay-250 hover:bg-sky-100" @click="click('0')">0</button>
            <button class="h-28 text-x1 text-black font-semibold bg-emerald-500 col-span-2 border-2 rounded-br-lg border-sky-300 transition ease-in-out delay-250 hover:bg-sky-100" @click="clickResult()">=</button>
          </div>
        </div>
    </div>
</template>

<script>
export default { 
    name: "CalculadoraGreen",
    data(){
      return{ 
        getOperation:'',
        getResult:'0',
      }
    },
    methods: {

      clickAC() { 
          this.getResult = "0";
          this.getOperation = "";
       },

      clickDEL(){ 
          if(this.getResult.length > 1){
            this.getResult = this.getResult.substring(0, this.getResult.length - 1);
          }else{
            this.getResult = "0";
          }
      },

      click(par){
        if(this.getResult == "0"){
          this.getResult = par;
        }else{ 
          this.getResult += par;
        }
      },

      clickResult(){
        let operation = this.getResult;
        this.getOperation = operation;

/*         operation=operation.replace("x","*");
        operation=operation.replace("","/"); */
        this.getResult= eval(operation);
      }
    },
}
</script>