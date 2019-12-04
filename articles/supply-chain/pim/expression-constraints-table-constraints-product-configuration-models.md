---
title: Restrições de expressão e restrições de tabela nos modelos de configuração do produto
description: Este tópico descreve o uso de restrições de expressão e de tabela. As restrições controlam os valores de atributo que podem ser selecionados quando você configura produtos para uma ordem de venda, cotação de venda, ordem de compra, ou uma ordem de produção. É possível usar restrições de expressão ou de tabela, dependendo de como você preferir criar as restrições.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91eb5f166633f5be0ad68c039d3e538e4060ea0b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815056"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>Restrições de expressão e restrições de tabela nos modelos de configuração do produto

[!include [banner](../includes/banner.md)]

Este tópico descreve o uso de restrições de expressão e de tabela. As restrições controlam os valores de atributo que podem ser selecionados quando você configura produtos para uma ordem de venda, cotação de venda, ordem de compra, ou uma ordem de produção. É possível usar restrições de expressão ou de tabela, dependendo de como você preferir criar as restrições. 

As restrições são usadas para controlar os valores de atributo que podem ser selecionados quando você configura produtos para uma ordem de venda, cotação de venda, ordem de compra ou uma ordem de produção. É possível usar restrições de expressão ou de tabela, dependendo de como você preferir criar as restrições.

## <a name="what-are-expression-constraints"></a>O que são as restrições de expressão?
As restrições de expressão são caracterizadas por uma expressão que usa operadores e funções aritméticos e boolianos. Uma restrição de expressão será criado para um determinado componente em um modelo de configuração de produto. Não pode ser reutilizada ou compartilhada com outro componente. No entanto, as restrições de expressão para um componente pode fazer referência a atributos dos subcomponentes do componente.

## <a name="what-are-table-constraints"></a>O que são as restrições de tabela?
As restrições de tabela listam as combinações de valores que são permitidas para os atributos quando você configura um produto. As definições de restrição de tabela podem ser usadas genericamente. Ao criar uma restrição de tabela para um componente em um modelo de configuração de produto, selecione uma definição de restrição de tabela. Para criar combinações que são permitidas, adicione tipos de atributos específicos aos componentes. Cada tipo de atributo possui um valor específico.

### <a name="example-of-a-table-constraint"></a>Exemplo de uma restrição de tabela

Este exemplo mostra como você pode limitar a configuração de um orador para especificar partes frontais e acabamentos do gabinete. A primeira tabela mostra as partes frontais e acabamentos dos gabinetes que geralmente estão disponíveis para a configuração. Os valores são definidos para os tipos de atributos **Acabamento do gabinete** e **Grade frontal**.

| Tipo de atributo | Valores                      |
|----------------|-----------------------------|
| Acabamento do gabinete | Preto, carvalho, branco, jacarandá |
| Grade frontal    | Preto, metal, branco         |

A tabela a seguir mostra as combinações que são definidas pela restrição da tabela **Cor e acabamento**. Usando a restrição de tabela, você pode configurar um alto-falante com o acabamento de de carvalho e uma grade preta, um acabamento de jacarandá e uma grade branca, e assim por diante.

| Concluir         | Grade                       |
|----------------|-----------------------------|
| Carvalho            | Preto                       |
| Jacarandá       | Branco                       |
| Branco          | Preto                       |
| Branco          | Branco                       |
| Preto          | Preto                       |
| Preto          | Metal                       | 

É possível criar restrições de tabela definidas pelo sistema e pelo usuário. Para obter mais informações, consulte [Restrições de tabela definidas pelo sistema e pelo usuário](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Qual sintaxe deve ser usada para gravar restrições?
Você deve usar a sintaxe do OML (Optimization Modeling Language) ao gravar restrições. O sistema usa o solver de restrição do Microsoft Solver Foundation para resolver as restrições.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>Devo usar as restrições de tabela ou restrições de expressão?
É possível usar restrições de expressão ou de tabela, dependendo de como você prefere criar as restrições. Você cria uma restrição de tabela como uma matriz, enquanto uma restrição da expressão é um demonstrativo individual. Ao configurar um produto, não importa o tipo de restrição que está sendo usado. O exemplo a seguir mostra como os dois métodos diferem.  

Quando você configura um produto usando as seguintes configurações de restrição, essas combinações são permitidas:

-   Um produto na cor preta com o tamanho 30 ou 50
-   Um produto na cor vermelha com o tamanho 20

### <a name="table-constraint-setup"></a>Configuração da restrição de tabela

| Cor | Tamanho |
|-------|------|
| Preto | 30   |
| Preto | 50   |
| Vermelho   | 20   |

### <a name="expression-constraint-setup"></a>Configuração de restrição de expressão

(Cor == "Preto" & (tamanho == "30" | tamanho == "50")) | (cor == "Vermelho" & tamanho = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>Devo usar operadores ou notação de infixo quando escrevo restrições de expressão?
É possível gravar uma restrição de expressão usando os operadores de prefixo disponíveis ou usando a notação de infixo. Para os operadores **Mín.**, **Máx.** e **Abs**, você não pode usar a notação de infixo. Estes operadores estão incluídos como operadores padrão na maioria das linguagens de programação.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>Quais operadores e notação de infixo posso usar ao gravar restrições de expressão?
As tabelas a seguir listam os operadores e as notações de infixo que você pode usar ao criar uma restrição de expressão para um componente em um modelo de configuração de produto. Os exemplos da primeira tabela mostram como gravar uma expressão usando os operadores ou a notação de infixo.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Operador</th>
<th>Descrição</th>
<th>Sintaxe</th>
<th>Exemplos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implies</td>
<td>Isso ocorre se a primeira condição for falsa, a segunda condição for verdadeira ou ambos.</td>
<td>Implies[a, b], infixo: a -: b</td>
<td><ul>
<li><strong>Operador:</strong> Implies[x != 0, y &gt;= 0]</li>
<li><strong>Notação de infixo:</strong> x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>E</td>
<td>Isso ocorre apenas se todas as condições forem verdadeiras. If the number of conditions is 0 (zero), ele produzirá <strong>Verdadeiro</strong>.</td>
<td>And[args], infixo: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>Operador:</strong> And[x == 2, y &lt;= 2]</li>
<li><strong>Notação de infixo:</strong> x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ou</td>
<td>Isso será verdadeiro se qualquer condição for verdadeira. Se o número de condições for 0, ele produzirá <strong>Falso</strong>.</td>
<td>Or[args], infixo: a | b | ... | z</td>
<td><ul>
<li><strong>Operador:</strong> Or[x == 2, y &lt;= 2]</li>
<li><strong>Notação de infixo:</strong> x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Mais</td>
<td>Isso soma as condições. Se o número de condições for 0, ele produzirá <strong>0</strong>.</td>
<td>Plus[args], infixo: a + b + ... + z</td>
<td><ul>
<li><strong>Operador:</strong> Plus[x, y, 2] == z</li>
<li><strong>Notação de infixo:</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Menos</td>
<td>Isso nega o argumento. Deve ter exatamente uma condição.</td>
<td>Minus[expr], infixo: -expr</td>
<td><ul>
<li><strong>Operador:</strong> Minus[x] == y</li>
<li><strong>Notação de infixo:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>Leva o valor absoluto da condição. Deve ter exatamente uma condição.</td>
<td>Abs[expr]</td>
<td><strong>Operador:</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Horas</td>
<td>Leva o produto das condições. Se o número de condições for 0, ele produzirá <strong>1</strong>.</td>
<td>Times[args], infixo: a * b * ... * z</td>
<td><ul>
<li><strong>Operador:</strong> Times[x, y, 2] == z</li>
<li><strong>Notação de infixo:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Energia</td>
<td>Leva um exponencial. Ele aplica a exponenciação da direita para a esquerda. (Ou seja, é associativo à direita). Consequentemente, <strong>Power[a, b, c]</strong> é equivalente a <strong>Power[a, Power[b, c]]</strong>. <strong>Potência</strong> pode ser usada somente se o expoente for uma constante positiva.</td>
<td>Power[args], infixo: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>Operador:</strong> Power[x, 2] == y</li>
<li><strong>Notação de infixo:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Máx.</td>
<td>Isso gera a condição a maior. Se o número de condições for 0, ele produzirá <strong>Infinito</strong>.</td>
<td>Max[args]</td>
<td><strong>Operador:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Mín.</td>
<td>Isso gera a condição menor. Se o número de condições for 0, ele produzirá <strong>Infinito</strong>.</td>
<td>Min[args]</td>
<td><strong>Operador:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Não</td>
<td>Isso gera a inversão lógica da condição. Deve ter exatamente uma condição.</td>
<td>Not[expr], infixo: !expr</td>
<td><ul>
<li><strong>Operador:</strong> Not[x] &amp; Not[y == 3]</li>
<li><strong>Notação de infixo:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Os exemplos na tabela a seguir mostram como gravar uma notação de infixo.


|  Notação de infixo   |                                          descrição                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     x + y + z     |                                           Adição                                            |
|    x \* y \* z    |                                        Multiplicação                                         |
|       x - y       | A subtração binária é traduzida da mesma forma de uma adição binária onde há um segundo binário. |
|     x ^ y ^ z     |                          Exponenciação com associabilidade direta                          |
|        !x         |                                          Não booliano                                          |
|      x -: y       |                                      Implicação booliana                                      |
|         x         |                                               y                                               |
|     x & y & z     |                                          E booliano                                          |
|    x == y == z    |                                           Igualdade                                            |
|    x != y != z    |                                           Distinto                                            |
|  x &lt; y &lt; z  |                                           Menor que                                           |
|  x &gt; y &gt; z  |                                         Maior que                                          |
| x &lt;= y &lt;= z |                                     Menor que ou igual a                                     |
| x &gt;= y &gt;= z |                                   Maior que ou igual a                                    |
|        (x)        |                           Precedência padrão de sobreposição de parênteses.                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Por que minhas restrições de expressão não são validadas corretamente?
Não é possível usar palavras-chave reservadas como nomes de atributos, componentes ou subcomponentes em um modelo de configuração de produto. Veja uma lista das palavras-chave reservadas que você não pode usar:

-   Teto
-   Elemento
-   Equivalente
-   Piso
-   Se
-   Menos
-   Maior
-   Implies
-   Log
-   Máx
-   Min.
-   Menos
-   Mais
-   Potência
-   Tempos
-   Slot
-   Modelo
-   Decisão
-   Meta


<a name="additional-resources"></a>Recursos adicionais
--------

[Criar uma restrição de expressão](tasks/add-expression-constraint-product-configuration-model.md)

[Adicionar um cálculo a um modelo de configuração de produto](tasks/add-calculation-product-configuration-model.md)



