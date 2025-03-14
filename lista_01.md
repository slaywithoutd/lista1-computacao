# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 
> Como foi usado o var para criar essa váriavel, ela *existe* em qualquer escopo, por isso não deu erro. Mas como ela só teve um valor atribuido depois do console.log já ter rodado, no momento em que x foi printado, x ainda não tinha valor, por isso foi printado "undefined".
> Já no caso do y, ele foi criado utilizando o let, então essa variavel só existe dentro do próprio escopo. Como o console.log estava fora do escopo dessa variavel, quando y foi printado, y ainda não existia, por isso o código deu erro.

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

b) O código imprime 200.
> Apesar de que se um humano olhar o código, conseguirá entender que o preço do "eletrônico" provavelmente é 1000, como um computador depende de instruções especificas para realizar uma função, e qualquer erro pode mudar completamente o resultado, nesse código a saída será 200. Isso acontece porque está faltando uma instrução break após o caso "eletrônico". Sem o break, o código continua executando os casos seguintes até chegar em um break, resultando no valor final de preço sendo 200.



______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
d) 24
> Primeiro temos uma array com os números de 1 à 5. No código, o método .map multiplica cada um dos elementos da array por 2, assim, o resultado desse método é uma nova array com os números [2, 4, 6, 8, 10]. Em seguida, o método .filter cria uma nova array, porém filtra os elementos que farão parte dela, apenas permitindo números maiores que 5, essa nova array será [6, 8, 10]. Por fim, o método .reduce está somando todos os elementos dessa array, assim, reduzindo a array em um unico valor, no caso, 0 + 6 + 8 + 10 = 24. Por isso, o resultado printado será 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```
c) ["banana", "abacaxi", "manga", "laranja"]
> O método .splice modifica uma array, removendo e/ou adicionando elementos. Nesse caso os números indicam de qual e até qual elemento da array algum elemento será retirado, assim, como os elementos começam a contar do 0, o elementos 1 e 2 são, respectivamente, maçã e uva, e esses serão os elementos que serão removidos. Os agumentos seguintes são os novos elementos que serão adicionados à array. Então, removendo do elemento 1 ao 2, a array fica: ["banana", "laranja"], em seguida, adicionando os novos elementos "abacaxi" e "manga" no lugar dos elementos removidos, a array fica: ["banana", "abacaxi", "manga", "laranja"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.

a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.
> I está correta pois a herança realmente permite que uma classe herde os métodos de outra sem necessidade de repetir código.
> II está correta e justifica a primeira afirmação porque é atraves da palavra-chave `extends` que a herença é implementada, permitindo que uma classe derive de outra

______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

> A classe Funcionario realmente herda de Pessoa e pode acessar nome e idade diretamente, pois a herança em JavaScript funciona com extends. Além disso, o método apresentar() de Funcionario sobrescreve o da classe Pessoa, mas ainda o chama usando super.apresentar(), garantindo que a apresentação original aconteça antes de exibir o salário. Já a afirmação III está errada, pois JavaScript suporta herança de classes.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

b) A asserção é verdadeira e a razão é falsa.

> O polimorfismo realmente permite que diferentes objetos respondam à mesma mensagem de formas distintas, como quando uma subclasse sobrescreve um método da classe pai. No entanto, a razão está errada porque JavaScript não suporta sobrecarga de métodos (definir múltiplos métodos com o mesmo nome e assinaturas diferentes). Em JavaScript, o polimorfismo ocorre principalmente por sobrescrita de métodos e pelo uso dinâmico de tipos.
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.
