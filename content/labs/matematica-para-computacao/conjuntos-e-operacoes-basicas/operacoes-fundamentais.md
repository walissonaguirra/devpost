---
title: "Operações Fundamentais"
date: 2026-05-04T20:25:00-03:00
draft: false
description: "Anotações sobre aritmética com números naturais: adição, subtração, multiplicação, divisão, sucessor, antecessor, múltiplos e divisores."
tags: ["Estudo", "Matematica para computação"]
---

## Aritmética com Números Naturais

O conjunto dos números naturais é:

$$\mathbb{N} = \lbrace 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, \dots \rbrace$$

A partir dele definimos as quatro operações básicas e algumas ideias derivadas como sucessor, antecessor, múltiplos e divisores.

## Adição
A adição em $\mathbb{N}$ tem quatro propriedades importantes:

1. **Comutatividade**: a ordem não altera o resultado.
2. **Associatividade**: o agrupamento não altera o resultado.
3. **Fechamento**: somar dois naturais sempre resulta num natural.
4. **Elemento neutro**: na adição é $0$ pois não altera o resultado.

```go {filename="main.go"}
// comutatividade
1 + 2 == 2 + 1 // true

// associatividade
2 + (3 + 1) == (1 + 2) + 3 // true

// 0 é o elemento neutro
7 + 0 == 7 // true
```

## Subtração
Diferente da adição, a subtração **não é comutativa** e nem sempre fica dentro de $\mathbb{N}$:

```go {filename="main.go"}
8 - 0 // 8
7 - 3 // 4

// não é comutativa
3 - 7 // -4 — sai do conjunto dos naturais
```

Ou seja, a subtração não tem fechamento em $\mathbb{N}$.

## Multiplicação
Vale para a multiplicação as mesmas quatro propriedades da adição, com uma diferença: o elemento neutro é o $1$.

A multiplicação tem ainda uma propriedade extra que liga ela à adição: a **distributividade**. Multiplicar um número por uma soma dá o mesmo resultado de multiplicar pelas duas parcelas separadas e somar depois: $a \times (b + c) = a \times b + a \times c$.

```go {filename="main.go"}
// comutatividade
7 * 8 == 8 * 7 // true

// associatividade
(7 * 8) * 9 == 8 * (7 * 9) // true

// elemento neutro
1 * 5 == 5 // true

// distributividade
2 * (3 + 4) == 2*3 + 2*4 // true
```

## Divisão
A divisão envolve quatro elementos:

- **dividendo**: o número que está sendo dividido
- **divisor**: por quem se divide
- **quociente**: o resultado inteiro da divisão
- **resto**: o que sobra

Em $8 \div 2$, temos dividendo $8$, divisor $2$, quociente $4$ e resto $0$. Como o resto é zero, dizemos que $2$ **divide** $8$, ou que $8$ **é divisível** por $2$.

Já em $9 \div 2$, o quociente é $4$ e o resto é $1$.

```go {filename="main.go"}
8 / 2 // 4 — quociente
9 / 2 // 4 — quociente, resto 1
9 % 2 // 1 — resto da divisão com o operador %
```

## Potenciação
A potenciação é uma multiplicação repetida. Em $a^n$, $a$ é a **base** e $n$ é o **expoente**, e o resultado é $a$ multiplicado por ele mesmo $n$ vezes:

$$a^n = \underbrace{a \times a \times \cdots \times a}_{n \text{ vezes}}$$

Dois casos especiais: $a^1 = a$ e $a^0 = 1$ (qualquer número elevado a zero é $1$).

Go não tem operador de potência para inteiros, então dá pra escrever uma função simples:

```go {filename="main.go"}
func potencia(a, n int) int {
    resultado := 1
    for i := 0; i < n; i++ {
        resultado *= a
    }
    return resultado
}

potencia(2, 3) // 8 = 2 * 2 * 2
potencia(5, 0) // 1
potencia(7, 1) // 7
```

## Sucessor
O sucessor de um número natural $n$ é simplesmente $n + 1$.

```go {filename="main.go"}
func sucessor(n int) int {
    return n + 1
}

sucessor(27) // 28
```

## Antecessor
O antecessor de $n$ é $n - 1$. Mas o $0$ não tem antecessor em $\mathbb{N}$, então é preciso tratar esse caso:

```go {filename="main.go"}
func antecessor(n int) (int, error) {
    if n == 0 {
        return 0, errors.New("zero não tem antecessor")
    }
    return n - 1, nil
}

antecessor(22) // 21, nil
```

## Múltiplos
Os múltiplos de um número $n$ são todos os naturais da forma $n \times \text{algumacoisa}$ ou, os números divisíveis por $n$.

Por exemplo, $8$ é múltiplo de $2$ porque $8 = 2 \times 4$.

```go {filename="main.go"}
// múltiplos de n até k
func multiplos(n, k int) []int {
    resposta := []int{}
    for i := 0; i <= k; i++ {
        resposta = append(resposta, n*i)
    }
    return resposta
}

multiplos(2, 10) // [0 2 4 6 8 10 12 14 16 18 20]
multiplos(3, 15) // [0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45]
```

## Divisores
O divisor de um número natural $n$ é um número que **divide** $n$, ou seja, $n$ é divisível por ele. Por exemplo, os divisores de $12$ são $1, 2, 3, 4, 6$ e $12$, porque cada um deles divide $12$ sem deixar resto.

```go {filename="main.go"}
func divisores(n int) []int {
    resposta := []int{}
    for i := 1; i <= n; i++ {
        if n%i == 0 {
            resposta = append(resposta, i)
        }
    }
    return resposta
}

divisores(12) // [1 2 3 4 6 12]
```

## Referências
- [Programação Dinâmica - Aritmética com Números Naturais](https://matematica.pgdinamica.com/conjuntos_e_operacoes_basicas/001operacoesfundamentais.html)
- [Universidade Estadual de Londrina - Introdução aos números naturais](https://www.uel.br/projetos/matessencial/basico/fundamental/naturais1.html)

