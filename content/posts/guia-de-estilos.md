---
title: "Guia de Estilos"
date: 2026-04-09T23:52:05-03:00
draft: true
toc: true
description: "Referência visual com todos os elementos suportados pelo tema: tipografia, listas, código, blockquotes e mais."
tags: ["meta", "estilo"]
---

Este post demonstra todos os elementos visuais disponíveis no tema.

## Índice (TOC)

Quando o frontmatter inclui `toc: true`, o tema gera automaticamente um índice com base nos headings do post. Útil para posts longos com várias seções.

## Parágrafos e texto inline

Este é um parágrafo normal com **negrito**, *itálico*, e texto `inline code` no meio da frase. Também é possível usar [links](https://exemplo.com) e combinar **negrito com *itálico***. Palavras em <dfn>versalete</dfn> usam small-caps.

## Headings

### Este é um h3

O h1 é reservado para o título do post. O h2 para seções e h3 para subseções.

## Listas

Lista não ordenada:

- Primeiro item
- Segundo item
  - Sub-item
  - Outro sub-item
- Terceiro item

Lista ordenada:

1. Primeiro passo
2. Segundo passo
3. Terceiro passo

## Links

Um [link normal](https://exemplo.com) e um link para email: [contato@exemplo.com](mailto:contato@exemplo.com).

## Citações

> Simplicidade é a sofisticação suprema.
> — Leonardo da Vinci

## Blocos de código

Código Go:

```go
package main

import "fmt"

func main() {
    msgs := []string{"olá", "mundo"}
    for _, msg := range msgs {
        fmt.Println(msg)
    }
}
```

Código PHP:

```php
<?php

function fibonacci(int $n): int
{
    if ($n <= 1) {
        return $n;
    }
    return fibonacci($n - 1) + fibonacci($n - 2);
}

echo fibonacci(10); // 55
```

Código shell:

```bash
#!/bin/bash
for file in *.go; do
    echo "Formatando $file"
    gofmt -w "$file"
done
```

## Tabelas

| Linguagem | Tipo         | Ano  |
|-----------|--------------|------|
| Go        | Compilada    | 2009 |
| PHP       | Interpretada | 1995 |
| Rust      | Compilada    | 2010 |
| Python    | Interpretada | 1991 |

## Imagens

![Exemplo de imagem](https://placehold.co/600x200/png?text=Exemplo+de+imagem "Legenda da imagem - fonte placehold.co")

## Linha horizontal

Conteúdo antes da linha.

---

Conteúdo depois da linha.

## Código inline em contexto

Use `go build` para compilar, `go test ./...` para testar e `go fmt` para formatar. A flag `-race` ativa o detector de data races.

## Atalhos de teclado

Para salvar use <kbd><kbd>Ctrl</kbd>+<kbd>S</kbd></kbd>. Para abrir o terminal use <kbd><kbd>Ctrl</kbd>+<kbd>`</kbd></kbd>. No macOS, substitua <kbd><kbd>Ctrl</kbd></kbd> por <kbd><kbd>⌘</kbd></kbd>.

## Admonição (nota)

<aside class="admn">
<svg class="icon" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/></svg>
<div>

Isso é uma nota informativa. Use para destacar algo importante que o leitor não deve perder.

</div>
</aside>

## Admonição (aviso)

<aside class="admn warn">
<svg class="icon" viewBox="0 0 24 24"><path d="M1 21h22L12 2 1 21zm12-3h-2v-2h2v2zm0-4h-2v-4h2v4z"/></svg>
<div>

Cuidado! Este é um aviso importante. Algo pode dar errado se você ignorar isso.

</div>
</aside>

## Bloco aside

<aside class="block">
<div class="title">Nota lateral</div>

Este é um bloco lateral com fundo cinza e borda. Útil para informações complementares que não fazem parte do fluxo principal do texto.

</aside>

## Details / Summary

<details>
<summary>Clique para expandir</summary>

Este conteúdo está escondido por padrão. O leitor pode expandir quando quiser. Útil para exemplos longos, logs de erro ou informações opcionais.

```go
func segredo() string {
    return "conteúdo escondido"
}
```

</details>

## Figura com legenda

<figure>
<img src="https://via.placeholder.com/500x200?text=Diagrama+de+arquitetura" alt="Diagrama de arquitetura">
<figcaption class="title">Figura 1. Diagrama simplificado da arquitetura do sistema.</figcaption>
</figure>

## Layout em duas colunas

<div class="two-col">
<div>

**Antes:**

```go
if err != nil {
    log.Fatal(err)
}
```

</div>
<div>

**Depois:**

```go
if err != nil {
    return fmt.Errorf("falha: %w", err)
}
```

</div>
</div>

## Lista de definições

<dl>
<dt>Go</dt>
<dd>Linguagem compilada criada pelo Google, focada em simplicidade e concorrência.</dd>
<dt>PHP</dt>
<dd>Linguagem interpretada amplamente usada em desenvolvimento web.</dd>
<dt>Monólito modular</dt>
<dd>Arquitetura onde a aplicação é um único deploy mas organizada em módulos com fronteiras bem definidas.</dd>
</dl>

## Sobrescrito e subscrito

A fórmula da água é H<sub>2</sub>O. A equação de Einstein: E = mc<sup>2</sup>.

## Matemática com KaTeX

Inline: a identidade de Euler é $e^{i\pi} + 1 = 0$.

Bloco:

$$
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
$$

A fórmula quadrática:

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

Somatório:

$$
\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}
$$

## Vídeo (YouTube)

{{< youtube 0RKpf3rK57I >}}

## Texto longo para demonstrar justify

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
