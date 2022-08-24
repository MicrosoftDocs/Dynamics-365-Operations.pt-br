---
title: Função de ER FORMAT
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) FORMAT é usada.
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: a7eb3d4a4c72e8faf40d28a724cda5ba7d7e8a47
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285989"
---
# <a name="format-er-function"></a>Função de ER FORMAT

[!include [banner](../includes/banner.md)]

A função `FORMAT` retorna a cadeia de caracteres especificada como um valor de *Cadeia de caracteres* após ela ser formatada, substituindo todas as ocorrências de **%N** pelo *N* º argumento.

## <a name="syntax"></a>Sintaxe

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Argumentos

`string`: *Cadeia de caracteres*

Uma referência a uma fonte de dados do tipo *Cadeia de caracteres* que deve ser formatada. Esse argumento é obrigatório.

`argument 1`: *Cadeia de caracteres*

O primeiro argumento, que é usado para substituir as ocorrências de **%1**. Esse argumento é obrigatório.

`argument N`: *Cadeia de caracteres*

O *N* º argumento, que é usado para substituir as ocorrências de **%2**, **%3** etc. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Se o argumento não é fornecido para um parâmetro, o parâmetro será devolvido como **"%N"** na cadeia de caracteres. Para valores do tipo *Real*, a conversão de cadeia de caracteres padrão é limitada a duas casas decimais.

## <a name="example"></a>Exemplo

Na ilustração a seguir, a fonte de dados **PaymentModel** retorna uma lista de registros de clientes usando o componente **Cliente**. Ela retorna o valor de data de processamento usando o campo **ProcessingDate**.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

No formato de relatório eletrônico (ER) que foi projetado para gerar um arquivo eletrônico para clientes selecionados, **PaymentModel** é selecionada como uma fonte de dados e controla o fluxo do processo. Se um cliente selecionado for interrompido na data em que o relatório é processado, uma exceção será gerada para informar o usuário. A fórmula que é criada para este tipo de controle de processamento pode usar os seguintes recursos:

- Rótulo SYS70894, que tem o texto a seguir:

    - **Para o idioma EN-US:** "Nothing to print"
    - **Para o idioma DE** "Nichts zu drucken"

- Rótulo SYS18389, que tem o texto a seguir:

    - **Para o idioma EN-US**: "Customer %1 is stopped for %2".
    - **Para o idioma DE**: "Debitor '%1' wird für %2 gesperrt".

Veja a expressão que pode ser criada.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Se um relatório for processado para o cliente **Litware Retail** em 17 de dezembro de 2015, na cultura **EN-US** e no idioma **EN-US**, esta fórmula retornará o seguinte texto, que pode ser apresentado ao usuário como uma mensagem de exceção.

*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*

Se o mesmo relatório for processado para o cliente **Litware Retail** em 17 de dezembro de 2015, na cultura **DE** e no idioma **DE**, esta fórmula retornará o seguinte texto, que usa um formato de data diferente:

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> A seguinte sintaxe será aplicada em fórmulas de ER para rótulos:
>
> - **Para rótulos de recursos no aplicativo Microsoft Dynamics 365 Finance:** **\@X**, onde **X** é a ID do rótulo na AOT (Árvore de Objetos de Aplicativo)
> - **Para rótulos que residem nas configurações de ER:** **@"GER_LABEL:X"**, onde **X** é a ID do rótulo na configuração de ER

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
