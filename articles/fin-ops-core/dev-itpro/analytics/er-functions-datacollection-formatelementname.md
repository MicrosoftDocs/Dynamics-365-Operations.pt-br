---
title: Função FORMATELEMENTNAME ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico FORMATELEMENTNAME é usada.
author: NickSelin
ms.date: 12/05/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a733c3c70cede6395b3d7454d82ce4d999e7e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851970"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]