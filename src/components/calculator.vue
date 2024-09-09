    <template>
        <div class="calculator card p-5 mx-auto" style="max-width: 600px;">
        <div class="form-group">
            <input
            type="number"
            class="form-control"
            v-model="num1"
            placeholder="Digite o primeiro número"
            />
        </div>
        
        <div class="form-group my-3">
            <input
            type="number"
            class="form-control"
            v-model="num2"
            placeholder="Digite o segundo número"
            />
        </div>

        <div class="form-group my-2">
            <select class="form-control" v-model="operation">
            <option value="+">Somar</option>
            <option value="-">Subtrair</option>
            <option value="*">Multiplicar</option>
            <option value="/">Dividir</option>
            </select>
        </div>
        
        <div class="result mt-4">
            <p class="h4 text-center">Resultado: {{ result }}</p>
        </div>
        </div>
    </template>
    
    <script>
    export default {
        name: 'Calculator',
        data() {
        return {
            num1: 0,
            num2: 0,
            operation: '+',
        };
        },
        computed: {
        result() {
            let n1 = parseFloat(this.num1);
            let n2 = parseFloat(this.num2);
    
            switch (this.operation) {
            case '+':
                return n1 + n2;
            case '-':
                return n1 - n2;
            case '*':
                return n1 * n2;
            case '/':
                return n2 !== 0 ? n1 / n2 : 'Erro (Divisão por 0)';
            default:
                return 0;
            }
        },
        },
    };
    </script>
        <style scoped>
        .result{
            color: rgb(47, 6, 6);
            border: solid 1px;
        }
        </style>
        