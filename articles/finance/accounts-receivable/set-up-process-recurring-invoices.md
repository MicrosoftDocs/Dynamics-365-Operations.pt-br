---
title: Configurar e processar notas ficais recorrentes
description: Este artigo explica como configurar e processar notas fiscais recorrentes. Você pode usar notas fiscais recorrentes se você deve cobrar clientes para a mesma quantidade regularmente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b155d163c57f3c917b4d87fae7cbd737e7c45fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971594"
---
# <a name="set-up-and-process-recurring-invoices"></a>Configurar e processar notas ficais recorrentes

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar e processar notas fiscais recorrentes. Você pode usar notas fiscais recorrentes se você deve cobrar clientes para a mesma quantidade regularmente.

<a name="create-a-recurring-free-text-invoice-template"></a>Criar um modelo de fatura de texto livre recorrente
---------------------------------------------

Para cobrar clientes sobre os mesmos serviços regularmente, você deve definir um modelo de fatura de texto livre que pode ser reutilizado para criar faturas. Este modelo contém as seguintes informações:

-   Informações do cabeçalho, como grupos de impostos, termos de pagamentos e métodos de pagamento
-   Informações da linha, como descrição do serviço, contas da receita, preço unitário e valor da fatura
-   Encargos de envio e manipulação
-   Distribuições contábeis com informações de dimensão financeira, como centros de custo e unidades de negócios

Na verdade, você está criando uma fatura e inteira e salvando como modelo. Você pode configurar o modelos usando a página **Faturas recorrentes**.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Atribuir um modelo de fatura de texto livre para um cliente e inserir os detalhes de recorrência
Depois que o modelo é criado, você deve atribuir o modelo aos clientes que você deseja cobrar. Além disso, você deve especificar quando e como a fatura será usada. Você pode atribuir os modelos na guia **fatura** na página **Clientes**. Adicione o modelo à lista e atualize as seguintes informações:

-   A data de início e, opcionalmente, a data final para a cobrança recorrente
-   A frequência de faturamento recorrente (por exemplo, cada dia ou uma vez por mês)
-   O valor máximo de cobrança (se essa informação for necessária)

Um cliente pode ter vários modelos que têm frequências diferentes.

## <a name="generate-the-recurring-invoices"></a>Gerar as faturas recorrentes
Na página **Faturas recorrentes**, há uma tarefa que processa modelos da fatura recorrente. Especifique a data da fatura e o modelo para gerar faturas. As faturas serão geradas e atribuídas a um único número de identificação de recorrência para cada grupo de faturas que é processado.

<a name="post-recurring-free-text-invoices"></a>Lançar faturas de texto livre recorrentes
---------------------------------

Depois que as faturas recorrentes são geradas, as IDs de recorrência da fatura aparecem em uma tarefa de lançamentos na página **Faturas recorrentes**. Você pode exibir todas as faturas para um ID de recorrência se você clicar no link. Durante a revisão de faturas para o ID de recorrência, você pode excluir faturas individuais. As configurações de recorrência do cliente serão redefinidas para esse modelo, de modo que possa ser gerado novamente depois. Você pode lançar uma, muitas ou todas as faturas para uma ID de recorrência. Se os fluxos de trabalho estiverem habilitados, você deverá clicar em **Enviar** antes de lançar as faturas.

<a name="print-recurring-free-text-invoices"></a>Imprimir faturas de texto livre recorrentes
----------------------------------

Depois que as faturas recorrentes são lançadas, você pode imprimir as faturas da página de listagem de faturas de texto livre. Você pode imprimir as faturas selecionadas ou pode selecionar um intervalo de faturas para imprimir.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]