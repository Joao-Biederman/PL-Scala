# PL-Scala
This repository was made as a draft for a work in the Programming Languages ​​class.

## Scala
Scala é uma linguagem de programação multiparadigma de propósito geral. Seu nome provem de **Scalabe Language**, ou Linguagem Escalavel, e é utilizada em diversos tipos diferentes de programas, desde programas onde se expera modularizacão e escalabilidade até para aplicações de Big Data. Sua flexibilidade se deve a diversos fatores, um destes sendo sua alta compatibilidade com Java, podendo ser compilado em Java bytecode e rodar em uma JVM (Java Virtual Machine). Outro fator que auxilia em sua popularidade e uso é a capacidade de utilizar bibliotecas e códigos já existentes no JAVA. A linguagem foi criada no intuido de ser um "JAVA melhorado", possuindo uma sintaxe semelhante, porém, diminuindo significativamente a quantidade de código necessário para executar rotinas de tarefas.

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
    AnyVal referencia qualquer valor no programa, desde letras até valores númericos e booleanos, qualquer variavel que diga respeito a um 

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
