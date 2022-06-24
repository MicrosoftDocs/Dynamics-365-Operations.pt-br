---
title: Definir os parâmetros de TDS
description: Este artigo explica como definir parâmetros para ativar a funcionalidade de Imposto Deduzido na Origem (TDS) em transações especificadas. Esta é uma etapa necessária para usar o recurso Imposto Deduzido na Origem (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3390cad6979858fbff73769d0d25132ba18a2157
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865603"
---
# <a name="set-the-tds-parameters"></a>Definir os parâmetros de TDS

[!include [banner](../includes/banner.md)]

Este artigo explica como definir parâmetros para ativar a funcionalidade de Imposto Deduzido na Origem (TDS) em transações especificadas. Esta é uma etapa necessária para usar o recurso Imposto Deduzido na Origem (TDS).

1. Acesse **Contabilidade \> Configuração do razão \> Parâmetros da contabilidade**.
2. Na guia **Impostos diretos**, na seção **Imposto Deduzido na Origem**, defina a opção **Ativar TDS** como **Sim** para ativar a funcionalidade de TDS e as páginas e campos que são usados para ela.
3. Defina a opção **Fatura** como **Sim** para ativar os campos que são usados para calcular e deduzir TDS no nível da fatura.
4. Defina a opção **Pagamento** como **Sim** para ativar os campos que são usados para calcular e deduzir TDS no nível do pagamento.

    [![Guia Impostos diretos.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. Na guia **Sequências de número**, localize a linha onde o campo **Referência** foi definido como **Pagamento de imposto retido na fonte**. No campo **Código de sequência numérica** da linha, selecione o código de sequência numérica. O código de sequência numérica é usado para gerar números do comprovante para o processo de liquidação TDS periódico.

    > [!NOTE]
    > Para executar o processo de liquidação de TDS periódico, Acesse **Imposto \> Declarações \> Imposto retido na fonte \> Pagamento de imposto retido na fonte**.

    [![Guia Sequências numéricas.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Feche a página.
