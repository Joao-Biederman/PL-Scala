# PL-Scala
This repository was made as a draft for a work in the Programming Languages ​​class.

## Scala
Scala é uma linguagem de programação de propósito geral, multiparadigma e de alto nível, pertencente à terceira geração de linguagens de programação. Foi lançada inicialmente em 2003 e recebe seu nome da abreviação de "Scalable Language" (Linguagem Escalável). Scala é amplamente utilizada em uma variedade de contextos, desde aplicações que exigem modularização e escalabilidade até projetos envolvendo Big Data. Sua flexibilidade é atribuída a diversos fatores, incluindo sua sólida compatibilidade com Java. Scala é compilada para Java bytecode e é executada na Máquina Virtual Java (JVM), o que facilita a integração com o ecossistema Java existente. A linguagem foi concebida com o objetivo de ser uma evolução do Java, mantendo uma sintaxe semelhante enquanto busca reduzir significativamente a quantidade de código necessária para realizar tarefas comuns. Esta abordagem conferiu a Scala uma reputação pela sua expressividade e concisão.

### Código
Os arquivos escritos em scala possuem a extensão .scala e podem ser executados com os comandos `scalac <nome do arquivo>.scala` para compilar o código e `scala <nome do objeto>` para executa-lo.
O código abaixo foi escrito, nomeado Hello.scala, como exemplo:
```Scala
object Hello {
    def main(args: Array[String]): Unit = {
        println("Hello world!")
    }
}
```
Ao compila-lo os arquivos "Hello.class", "Hello.tasty" e "Hello$.class" foram gerados e ao executar o comando `scala Hello` a frase "Hello world!" foi escrita no terminal.

### Tipagem
Em Scala, todos os valores são objetos, tendo seus tipos referenciados por classes.
Os tipos em Scala formam uma hierarquia, esta podendo ser representada da seguinte maneira
+ Any
    + AnyVal
        + Double
        + Float
        + Long
        + Int
        + Short
        + Byte
        + Unit
        + Boolean
        + Char
    + AnyReference
        + List
        + Option
        + "Classes"

#### Any
Any é um tipo que pode referenciar qualquer tipo dentro do programa, seja este qual for.

#### AnyVal
AnyVal referencia qualquer valor no programa, desde letras até valores númericos e booleanos, qualquer variavel que diga respeito a um valor.

#### AnyReference
AnyReference diz respeito a variaveis que não possuem um valor. Variaveis não valoradas em Scala são variaveis cujo tipo é uma referencia. Este tipo é correspondente com o tipo "java.lang.Object" do JAVA.

#### Double
Ponto flutuante de precisão dupla de 64 bits padrão IEEE 754

#### Float
Ponto flutuante de precisão sinples de 32 bits padrão IEEE 754

#### Long
Inteiro de 64 bits sinalizado de -9223372036854775808 até 9223372036854775807

#### Int
Inteiro de 32 bits sinalizado de -2147483648 até 2147483647

#### Short
Inteiro de 16 bits sinalizado de -32768 até 32767

#### Byte
Inteiro de 8 bits sinalizado de -128 até 127

#### Unit
Unit é um tipo que não traz nenhum valor. Ainda assim é muito utilizado uma vez que todas funções em Scala devem returnar um valor, funções podem retornar um tipo Unit, que é um tipo de valor que não atribui valor algum.

#### Boolean
Valores de verdadeiro e falso (true or false)

#### Char
Um Unicode de 16 bits cujo alcance vai de U+0000 até U+FFFF

#### List
Um ponteiro para uma lista de itens de algum tipo.

#### Option
Tipo que representa um valor opcional no código. Uma variável do tipo Option deve prover um tipo bem definido para a opção, e pode receber um item do tipo da variável ou nenhum valor. 

#### Classes
Tipo que representa uma classe com atributos e métodos.

#### NULL
Subtipo do tipo referencia quando está não referencia nada

#### Nothing
Subtipo para todos os tipos, incluindo NULL, não indica nenhum valor.

### Estruturas de controle
#### If/else/else if
Estrutura que impede a execução de uma parte do código a menos que uma condição seja atendida. Condições são expressões e o if retornará o resultado dela.

#### For
Estrutura para criação de loops, percorre uma lista de itens e executa o código designado até percorrer toda a lista.

#### Try/Catch
Try executa um código, Catch encontra o código de erro para que ele possa ser tratado.

#### Match
Varios casos são criados, cada um com um valor e um código, um valor é utilizado como entrada. Caso o valor sejá igual um dos casos seu respectivo código será executado.

### Funções
Em Scala funções podem ser declaradas como funções anônimas ou nomeadas. 
Funções anônimas não possuem um nome e são declaradas como `(x: Int) => x+1`, onde entre parenteses estão os parâmetros e depois da seta está a expressão correspondente a está função. Funções nomeadas possuem a sintaxe `val addOne = (x: Int) => x+1`. Tanto o prefixo val quanto def podem ser utilizados para definir uma função, com a diferença entre estes é quando utilizado def a função é avaliada quando a função é chamada, enquanto val avalia a função ao compila-la. Ao chamar uma função definida com def uma nova instância desta função é criada, fazendo com que cada chamada sejá considerada diferente das outras.
Funções podem retornar um ou mais valores, este valor podendo ser do tipo Unit, ou seja, não retornar nada.
Como funções nesta linguagme são objetos estes podem ser passados como parâmetro para uma função conforme mostrado no exemplo a seguir:
```Scala
object Main {
    def fazConta(callback: (Int, Int) => Int, x: Int, y: Int) { // Definimos um parâmentro que é uma função chamada callback, que para dois inteiros realiza uma função passada como parametro com retorno inteiro, tendo como parâmetros x e y.
      println(callback(x, y))
    }

    def main(args: Array[String]) {
        fazConta((x, y) => x + y, 5, 6); // Chamamos fazConta de (x,y), onde definimos como parâmetros uma nova função x+y e os valores 5 e 6
    }
}
```
###### Código por [DEVMEDIA](https://www.devmedia.com.br/conheca-a-linguagem-scala/32850)

Scala traz a possibilidade de escrever códigos tanto em POO quanto em programação funcional. As funções em Scala podem ser separadas em dois grupos: Funções puras e Funções impuras.

#### Funções Puras
Funções puras, segundo Alvin Alexander, são funções onde o resultado depende somende dos valores inseridos na função, não podendo receber nenhum valor externo aos inputs (vindas do console ou de um banco de dados por exemplo), e que não promova nenhuma mudança em estados escondidos.
As funções do pacote matemático de Scala são `abs`, `ceil`, `max`, `min`. Funções do pacote de Strings são `isEmpty`, `length` e `substring`. Metodos de funções também podem ser funções puras, alguns representantes de grupo são `drop`, `filter` e `map`.
Funções puras podem ser escritas desde que seguidas as regras citadas acima.
Exemplo de função pura escrita:
```Scala
def sum(list: List[Int]): Int = list match {
    case Nil => 0
    case head :: tail => head + sum(tail)
}
```

#### Funções impuras
São funções que alteram os parametros ou valores escondidos na função, acessam dados que não foram explicitamente passadas como parametros ou cujo retorno não dependente dos dados inseridos. Funções cujo retorno é do tipo Unit são um exemplo, uma vez que este tipo, apesar de ser um subtipo de valor, não retorna nada.
```Scala
object Contas {
    def soma(a: Int, b: Int): Int  =  a + b // Função pura que retorna a soma de a e b

    var y = 7;
    def sub(x: Int): Int = x - y // Função impura que retorna a subtração de x com y

    def main(args: Array[String]): Unit = {
        println(soma(2,2)) // Resultado esperado == 4
        println(sub(8)) // Resultado esperado == 1
    }
}
```
###### Código baseado em [Raquel Fontenelle](https://blog.cod3r.com.br/funcoes-puras-e-impuras/)

Paradigma Funcional: Estudo Comparativo

    Tipos de Dados e Listas

    Estruturas de Controle

    Funções (Primitivas, Numéricas, Especiais, Outras) e Notação Lambda

    Formas Especiais, Formas Funcionais

    Aplicação de Função

    Estruturas para Representar Dados

Paradigma Funcional: Relatório Prático

    Caracterizar a linguagem quanto ao propósito, execução, nível, paradigma, geração e tipagem

    Descrever instalação, tipos de dados básicos, palavras-chave, operadores, sentenças e funções da linguagem

    Exemplos de aplicação dos conceitos de tipos de dados e listas na linguagem

    Exemplos de aplicação dos conceitos de estruturas de controle na linguagem

    Exemplos de aplicação dos conceitos de funções e notação lambda na linguagem

    Exemplos de aplicação dos conceitos de formas especiais e formas funcionais na linguagem

    Exemplos de aplicação dos conceitos de aplicação de função na linguagem

    <!-- Exemplos de aplicação dos conceitos de estruturas para representar dados na linguagem -->