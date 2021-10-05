# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Instruções De Sistema - Statements - Java 
</h1>

<br>

# Instruções de Salto (jump statements)

<br>

## break
Este nos permite finalizar a instrução dentro da qual foi chamado, dando assim prosseguimento ao código fora da instrução. Logo, se chamado dentro de um loop ele finaliza o loop, tendo este loop finalizado suas interações ou não.

<br>

## continue
Este nos permite sair da interação da instrução dentro da qual foi chamado para a próxima interação da mesma instrução. Logo, se chamado dentro de um loop, ele para a interação atual e segue para a próxima interação deste mesmo loop.

<br>
<br>

# Instruções de Tomadas de decisão

<br>

## if / if ... else / if ... else if ... else
```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var condicao = true;

        if(condicao) {
            // faça isso pois a condição a verdadeira
        }

        if (condicao) {
            // faça isso pois a condição a verdadeira
        }else{
            // faça isso pois a condição é falsa
        }

        if (condicao) {
            // se condicao verdadeira
        } else if (condicao == false) {
            // se outra condicao verdadeira
        } else if (condicao == 10) {
            // se outra condicao verdadeira
        } else {
            // se nenhuma das condições acima for verdadeira
        }
    }
}
```

<br>

## Switch
Este nos permite testar se uma variável tem o valor igual a um dos valores contidos em uma lista de valores. Cada valor é referido como um `case`. Observe a sintáxe abaixo:

```java
switch(an_expression) {
    case value:
        // Statement(s)
        break; //optional
    case value:
        // Statement(s)
        break; //optional
    default : //Optional
        // Statement(s)
}
```

> Note a palavra reservada `break`, ela é uma instrução de salto (Jump Statement). Seu uso é opcional dentro de um `case`. 

<br>

O Switch só irá parar quando encontrar a instrução `break`. O programa irá pular então para a próxima linha fora do fluxo em que o break foi inserido. Porém, note que não é uma obrigação adicionar o `break` para cada `case` pois o `default` case pode ser adicionado ao final do switch, o caso default irá rodar no caso de nenhum `case` corresponder a verdadeiro.  

```java
package com.rodrigofentanes;

public class Programa {
    public static void main (String [] args){
        int numero = 10;
        switch (numero){
            case 10:
                System.out.println("Dez"); //Imprime: Dez
                break;
            case 20:
                System.out.println("Vinte");
                break;
            default:
                System.out.println("Outro número qualquer");
        }
    }
}
```



<br>

## Ternário
```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        final var condicao = false;
        final var ternario = condicao ? "é verdadeira" : "é falsa";
        System.out.println(ternario); // vai imprimir "é falsa"
        
    }
}
```

<br>
<br>

# Instruções de Repetição (Loop)
Estas nos ajudam a fazer tarefas repetitivas. Loops executam instruções de forma sequencial, ou seja, a primeira instrução roda, depois a segunda, depois a terceira e assim por diante. Abaixo as instruções de repetição suportadas pela linguagem Java:
-   while
-   do...while
-   for
-   foreach

## while
Enquanto algo for verdadeiro, faça. Primeiro testa depois faz.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var i = 0;
        while(i == 100){
            System.out.println(i);
            i++;
        }
        // Nada à imprimir
    }
}
```

<br>

## do while
Faça, enquanto isso for verdade. Primeiro faz depois testa.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var i = 0;
        do{
            System.out.println(i);
            i++;
        }while(i == 100);
        // Imprime: 0
    }
}
```

> A diferença entre o `while` e o `do..while` é que o `do...while` sempre será executado pelo menos uma vez, enquanto o `while` pode não rodar vez alguma a depender da condição apresentada.

<br>

## for
O `for` é uma estrutura de três partes:
1.   A condição inicial
2.   A condição que será verificada em TODAS, inclusive no início, as repetições/interações de um `for` e , sendo a condição verdadeira, entramos na nossa estrutura de laço. Caso esta condição seja falsa, automaticamente, o programa finaliza a execução da instrução.
3.   A ação de será executada ao final de cada interação.

Sintáxe:

```java
for(condicao_inicial ; condicao_de_verificacao ; acao) {
    // instrução
}
```

<br>

Exemplo:
```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        for(int i = 0; i <= 10; i = i++){
            //faz isso
        }
    }
}
```

<br>

## forEach
"Para cada" faça.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        IntStream.of(1,2,3,4,5).forEach( n -> {
            // faça isso
        });

        IntStream.range(0,3).forEach( n -> {
            // faça isso
        });
    }
}
```