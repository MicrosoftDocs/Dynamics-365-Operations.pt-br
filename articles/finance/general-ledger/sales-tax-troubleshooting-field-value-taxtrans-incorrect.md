---
title: Valor de campo incorreto em TaxTrans
description: Este tópico fornece informações sobre como solucionar problemas de valores de campo incorretos em TaxTrans.
author: EricWangChen
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6d4e7fd1bae56c5a7cb9a1a558a5344b3e555e83
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687578"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Valor de campo incorreto em TaxTrans

[!include [banner](../includes/banner.md)]

Se um valor de campo em **TaxTrans** estiver incorreto, use as informações deste tópico para tentar resolver o problema.

## <a name="overview-of-values"></a>Visão geral de valores
A lista a seguir mostra como **TaxTrans**, **TaxUncommitted** e **TmpTaxWorkTrans** são conjuntos de dados semelhantes, mas trabalham de forma diferente.

  - **TaxTrans** é o resultado da transação de imposto lançado final persistente no banco de dados.
  - **TaxUncommitted** é o resultado do imposto calculado intermediário persistente no banco de dados (se aplicável), que será usado posteriormente no lançamento.
  - **TmpTaxWorkTrans** é o resultado do imposto calculado temporário da tabela na memória (Tipo de Tabela = InMemory).

Se você encontrar a causa raiz de uma coluna **TaxTrans** incorreta, também encontrará a causa raiz de uma coluna **TaxUncommitted** ou **TmpTaxWorkTrans** incorreta. Isso ocorre porque as três colunas são copiadas uma da outra.

Normalmente, durante o cálculo de impostos, **TmpTaxWorkTrans** é gerado e, em seguida, se aplicável, **TaxUncommitted** é gerado. Durante o lançamento de impostos, **TaxTrans** é gerado.


## <a name="add-breakpoints"></a>Adicionar pontos de interrupção
Para adicionar pontos de interrupção, conclua as seguintes etapas: 

1. Adicione extensões e pontos de interrupção em *insert()* e *update()* nas extensões, conforme mostrado a seguir.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. Como alternativa, você pode adicionar pontos de interrupção diretamente quando **TaxUncommitted** não estiver incluído.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Reproduzir e depurar

Depois que os pontos de interrupção são definidos, todas as alterações de persistência de dados ficam visíveis durante a depuração. Para encontrar a causa raiz de uma coluna incorreta de **TaxTrans**, **TaxUncommitted** ou **TmpTaxWorkTrans**, revise e anote os seguintes itens:

- O último ponto de interrupção no qual a coluna está correta.
- O primeiro ponto de interrupção no qual a coluna está incorreta.
- O que acontece entre esses dois pontos.

## <a name="determine-whether-customization-exists"></a>Determinar se há personalização
Se você concluiu as etapas nas seções anteriores, mas não conseguiu resolver o problema, determine se há personalização. Se não houver personalização, contate o Suporte da Microsoft para obter ajuda.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

