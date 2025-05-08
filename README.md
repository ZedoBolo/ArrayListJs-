#  ArrayListJs

Tutorial do map, reduce e filter em arrays no JS.

---

##  Métodos de Array no JavaScript

###  1. map()

A função `map()` serve para modificar arrays. Ela passa por cada elemento de um array original, aplica uma função a cada um e gera um novo array com os resultados obtidos. O array original permanece inalterado. É perfeito para situações em que desejamos alterar os dados de maneira consistente, como multiplicar valores, transformar texto ou obter características de objetos.

 **Pontos positivos**:  código mais organizado, preserva o original.  
 
 **Ponto negativo**: pode usar mais memória se o novo array não for necessário.

####  Exemplos:

```
const array1 = [1, 4, 9, 16];
const map1 = array1.map(x => x * 2);
console.log(map1); // [2, 8, 18, 32]

---------------------------------------------

const users = [
  { id: 1, nome: "João" },
  { id: 2, nome: "Antonio" },
  { id: 3, nome: "Rodrigues" }
];
console.log(users.map(user => user.nome));
// ["João", "Antonio", "Rodrigues"]

--------------------------------------------------

const frutas = ["maçã", "banana", "laranja"];
const frutasMaiusculas = frutas.map(fruta => fruta.toUpperCase());
console.log(frutasMaiusculas);  
// ["MAÇÃ", "BANANA", "LARANJA"]
```
### 2. filter()
    
A função `filter()` é utilizada para selecionar elementos de um array segundo uma regra. Ela analisa cada item e preserva no novo array apenas aqueles que satisfazem a condição estabelecida, retornando verdadeiro. Isso é extremamente prático quando desejamos escolher itens determinados, como números pares, indivíduos adultos, produtos em promoção, entre outros.

**Pontos positivos**: preserva o array original, excelente para seleção.

**Ponto negativo**: consumo desnecessário de memória se o resultado não for armazenado.

 Exemplos:
```
const numeros = [1, 2, 3, 4, 5, 6];
const pares = numeros.filter(n => n % 2 === 0);
console.log(pares); // [2, 4, 6]

const pessoas = [
  { nome: "João", idade: 17 },
  { nome: "Maria", idade: 22 },
  { nome: "José", idade: 19 }
];

---------------------------------------------

const maioresDeIdade = pessoas.filter(pessoa => pessoa.idade >= 18);
console.log(maioresDeIdade);
// [ { nome: "Maria", idade: 22 }, { nome: "José", idade: 19 } ]

const numeros = [1, 2, 3, 4, 5, 6];

---------------------------------------------

const palavras = ["casa", "carro", "avião", "computador", "sol"];

const palavrasGrandes = palavras.filter(palavra => palavra.length > 5);
console.log(palavrasGrandes); // ["avião", "computador"]


```
### 3. reduce()

A função `reduce()` é utilizada para converter um array em um único valor, acumulando os resultados de forma incremental. Pode ser aplicada para somar valores, calcular médias, concatenar strings, contar elementos, entre outras atividades. Ao contrário do map e do filter, o reduce não gera um novo array — ele produz apenas um único valor (como um total, por exemplo).nto.

**Pontos positivos**: forte e eficaz para compilar informações.

**Ponto negativo**: menos fácil de entender para quem está começando.
 Exemplos:
```
const numeros = [1, 2, 3, 4];
const soma = numeros.reduce((acc, n) => acc + n, 0);
console.log(soma); // 10

---------------------------------------------

const carrinho = [
  { produto: "Camisa", preco: 50 },
  { produto: "Calça", preco: 80 },
  { produto: "Tênis", preco: 120 }
];

const total = carrinho.reduce((acc, item) => acc + item.preco, 0);
console.log(total); // 250


---------------------------------------------

const notas = [7, 8, 6, 10];

const media = notas.reduce((acc, nota) => acc + nota, 0) / notas.length;
console.log(media); // 7.75

```

