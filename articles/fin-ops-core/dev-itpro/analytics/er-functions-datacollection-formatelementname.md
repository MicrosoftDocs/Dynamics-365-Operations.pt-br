---
title: Função FORMATELEMENTNAME ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico FORMATELEMENTNAME é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: e8be55d9a90e841d64288b0c618c0012912ddbab
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745624"
---
# <a name="formatelementname-er-function"></a>Função FORMATELEMENTNAME ER

[!include [banner](../includes/banner.md)]

A função `FORMATELEMENTNAME` retorna um valor de *Cadeia de caracteres* que representa o nome do elemento do formato de relatório eletrônico (ER) atual.

## <a name="syntax"></a>Sintaxe

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Essa função pode ser chamada em expressões de ER que foram configuradas para propriedades **Nome da chave de dados coletada** e **Valor da chave de dados coletada** de um componente de formato ER do grupo **Texto** que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

## <a name="example"></a>Exemplo

Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de coleta de dados](er-functions-category-data-collection.md)
