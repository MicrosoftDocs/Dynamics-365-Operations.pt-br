---
title: Lista de funções ER na categoria específica do domínio empresarial
description: Este tópico fornece informações sobre as funções específicas de domínio empresarial que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 8f7612e83d9f30281e2b1a783275365459e67a40
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686114"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Lista de funções ER na categoria específica do domínio empresarial

[!include [banner](../includes/banner.md)]

Funções específicas de domínio de relatório eletrônico (ER) podem ser usadas para executar cálculos e solicitações de acesso a dados que são específicas para a implementação do Microsoft Dynamics 365 Finance. Este tópico fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função| Descrição |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD10, com base nos dígitos do número de fatura especificado. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa uma única ID de dimensão financeira obtida da cadeia de caracteres especificada. A cadeira de caracteres específicos apresenta todas as dimensões como uma lista de IDs separadas por vírgulas. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Essa função retorna um valor *Real* que representa o resultado da conversão do valor monetário especificado da moeda de origem especificada para a moeda de destino especificada usando as configurações da empresa especificada na data especificada. |
| [CurCredRef](er-functions-other-curcredref.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa uma referência de credor, com base nos dígitos do número de fatura especificado. |
| [FA_Balance](er-functions-other-fabalance.md) | Essa função retorna um valor de *Contêiner (registro)* que consiste em dados do saldo de ativo fixo para o item de ativo fixo, o código do método de depreciação, o ano do relatório e a data do relatório especificados. |
| [FA_Sum](er-functions-other-fasum.md) | Essa função retorna um valor de *Contêiner (registro)* que consiste em dados dos valores de ativo fixo para o item de ativo fixo, o código do método de depreciação e o período de datas especificados. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa o código da entidade legal (empresa) à qual um usuário está conectado no momento. |
| [ISOCredRef](er-functions-other-isocredref.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa uma referência de credor ISO (Organização Internacional de Normalização), com base nos dígitos e símbolos alfabéticos do número de fatura especificado. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Essa função retorna um valor *Booliano* de **TRUE** se a cadeia de caracteres especificada representar um IBAN (Número de Conta Bancária Internacional) válido. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [Mod_97](er-functions-other-mod97.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD97, com base nos dígitos do número de fatura especificado. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa o novo valor gerado de uma sequência numérica, com base na sequência numérica, no escopo e na ID do escopo especificados. A ID do escopo é igual ao código da empresa que é fornecido pelo contexto no qual o formato de ER é executado. |
| [RoundAmount](er-functions-other-roundamount.md) | Essa função retorna um valor *Real* que representa o resultado do arredondamento do valor especificado de casas decimais de acordo com a regra de arredondamento especificado. |
| [TableName2ID](er-functions-other-tablename2id.md) | Essa função retorna uma representação numérica da ID da tabela para o nome de tabela especificado como um valor *Inteiro*. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
