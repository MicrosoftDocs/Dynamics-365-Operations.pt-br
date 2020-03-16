---
title: Função de ER NUMSEQVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMSEQVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbe5e5ac17af743f8293e4255d9713b528182f66
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041299"
---
# <a name="NUMSEQVALUE">Função de ER NUMSEQVALUE</a>

[!include [banner](../includes/banner.md)]

A função `NUMSEQVALUE` retorna um valor de *Cadeia de caracteres* que representa o novo valor gerado de uma sequência numérica, com base na sequência numérica, no escopo e na ID do escopo especificados. A ID do escopo é igual ao código da empresa que é fornecido pelo contexto no qual o formato de relatório eletrônico (ER) é executado.

## <a name="syntax-1"></a>Sintaxe 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Sintaxe 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Argumentos

`number sequence code`: *Cadeia de caracteres*

Um valor de texto que representa o código da sequência numérica em que um novo valor é necessário.

`number sequence record ID`: *Int64*

Um valor *Int64* que representa a ID de registro de um registro na tabela NumberSequenceTable que contém a definição da sequência numérica em que um novo valor é necessário.

`scope type`: *Valor de enumeração*

Um valor de enumeração da enumeração **ERExpressionNumberSequenceScopeType** que define o escopo da sequência numérica em que um novo valor é necessário. Os tipos de escopo disponíveis são **Compartilhado**, **Entidade legal** e **Empresa**.

`scope ID`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que identifica o escopo, com base no tipo de escopo especificado.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Para o tipo de escopo **Compartilhado**, especifique uma cadeia de caracteres vazia como a ID do escopo.

Para os tipos de escopo **Empresa** e **Entidade legal**, especifique o código da empresa como a ID do escopo. Se você especificar uma cadeia de caracteres vazia como a ID do escopo para esses tipos de escopo, o código atual da empresa será usado.

Quando a sintaxe 1 é usada, a sequência numérica é solicitada para o tipo de escopo **Empresa** e o código da empresa é fornecido pelo contexto no qual o formato de ER é executado.

## <a name="example-1"></a>Exemplo 1

No formato de ER, você define a fonte de dados **AskNumSeq** do tipo *Parâmetro de entrada de usuário*. Essa fonte de dados se refere ao tipo de dados estendido (EDT) da **Descrição**. Em seguida, você define a fonte de dados **NumSeq** do tipo *Campo calculado*. Essa fonte de dados contém a expressão `NUMSEQVALUE (AskNumSeq)`. Quando a fonte de dados **NumSeq** é chamada, ela retorna o novo valor gerado da sequência numérica especificada no tempo de execução inserindo seu código na caixa de diálogo. A sequência numérica é solicitada para o tipo de escopo **Empresa**. O código da empresa é fornecido pelo contexto no qual o formato de ER é executado.

## <a name="example-2"></a>Exemplo 2

As seguintes fontes de dados são definidas no mapeamento de modelo:

- A fonte de dados **LedgerParms** do tipo *Tabela*. Essa fonte de dados se refere à tabela LedgerParameters.
- A fonte de dados **NumSeq** do tipo *Campo calculado*. Essa fonte de dados contém a expressão `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.

Quando a fonte de dados **NumSeq** é chamada, ela retorna o novo valor gerado da sequência numérica que foi configurado em parâmetros de contabilidade para a empresa que fornece o contexto no qual o formato ER é executado. Esta sequência numérica identifica exclusivamente diários e funciona como o número de lote que vincula as transações juntas.

## <a name="example-3"></a>Exemplo 3

As seguintes fontes de dados são definidas no mapeamento de modelo:

- A fonte de dados **enumScope** do tipo *enumeração* do Microsoft Dynamics 365 Finance. Essa fonte de dados se refere à enumeração **ERExpressionNumberSequenceScopeType**.
- A fonte de dados **NumSeq** do tipo *Campo calculado*. Essa fonte de dados contém a expressão `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.

Quando a fonte de dados **NumSeq** é chamada, ela retorna o novo valor gerado da sequência numérica **Gene\_1** que foi configurado para a empresa que fornece o contexto no qual o formato ER é executado.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)
