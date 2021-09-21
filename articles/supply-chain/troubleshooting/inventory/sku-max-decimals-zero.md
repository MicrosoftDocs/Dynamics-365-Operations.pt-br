---
title: O número máximo de casas decimais para a unidade de manutenção de estoque é 0
description: Ao tentar lançar uma transação de estoque ou uma reserva de estoque, você recebe a seguinte mensagem de erro "O número máximo de decimais para a unidade de manutenção de estoque é 0".
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475619"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>O número máximo de casas decimais para a unidade de manutenção de estoque é 0


## <a name="symptoms"></a>Sintomas

Ao tentar lançar uma transação de estoque ou uma reserva de estoque, você receberá a seguinte mensagem de erro:

> O número máximo de casas decimais para a unidade de manutenção de estoque é 0.

Esse problema ocorre quando a quantidade da transação de estoque é especificada como um valor decimal que está abaixo do nível de precisão ao qual o campo oferece suporte. Por exemplo, uma quantidade de *0,5* foi especificada para uma transação de estoque, mas só há suporte para quantidades inteiras. Portanto, o valor deve ser *1* em vez de *0,5*.

## <a name="resolution"></a>Resolução

1. Execute o script a seguir na sua instância do SQL Server para arredondar quantidades nas transações de estoque. Esse script corrigirá os valores na tabela **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Execute uma verificação de consistência disponível na qual a opção **corrigir erro** esteja ativada. Essa verificação corrigirá os valores na tabela **inventSum**.

> [!IMPORTANT]
> É altamente recomendável editar o script com cuidado conforme necessário para o seu ambiente, testá-lo em um ambiente de teste e verificar os dados resultantes antes de executá-lo em um ambiente de produção.
