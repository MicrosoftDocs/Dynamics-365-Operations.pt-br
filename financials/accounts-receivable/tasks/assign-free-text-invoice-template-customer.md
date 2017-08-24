--- 
title: Atribuir um modelo de fatura de texto livre a um cliente
description: Essa tarefa demonstra como atribuir um modelo de nota fiscal de texto livre a um cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: af9e5f499e6c162189443d95c90b15c17d910739
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Atribuir um modelo de fatura de texto livre a um cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Essa tarefa demonstra como atribuir um modelo de nota fiscal de texto livre a um cliente. Esta tarefa usa a empresa de demonstração USMF e é direcionada para o usuário responsável por gerenciar e processar faturas A/R.

1. Ir para Contas recebíveis > Clientes > Todos os clientes.
2. Na lista, localize e selecione o PDV desejado.
3. No Painel de Ação, clique em Fatura.
4. Clique em Faturas recorrentes.
    * Use esta página para atribuir modelos de fatura de texto livre para clientes e especificar quão frequentemente as faturas serão enviadas ao cliente.  
5. Clique em Novo para atribuir um novo modelo ao cliente.
6. Selecionar o modelo de fatura de texto livre que você deseja atribuir ao cliente.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. Insira a data em que a primeira fatura será gerada.
    * Insira uma data final de devolução.  
    * Selecione uma das seguintes opções: Nenhuma data final – as notas fiscais serão geradas indefinidamente até que o modelo seja removido da conta do cliente.  Data de término da cobrança - Selecione esta opção e insira a última data em que a fatura pode ser gerada.  
    * A geração de acumulação máxima de valor após o qual a nota fiscal será interrompida.  
    * Insira o valor cumulativo máximo que pode ser alcançado usando o modelo selecionado. Por exemplo, se você inserir 1.000,00 e gerar notas fiscais mensais para cada 100,00, as notas fiscais encerrarão a produção após a décima nota fiscal gerada.  
    * Gerenciar notas fiscais recorrentes usando os valores padrão do modelo de nota fiscal de texto livre ou da conta do cliente.  
    * Opte por usar o modelo de fatura de texto livre ou a conta do cliente para determinar os valores padrão para o idioma, o perfil de lançamentos, o grupo de impostos, o grupo de impostos do item, o código de lista, o país/região para entrega, a moeda, as condições de pagamento, o método de pagamento, as especificações de pagamento, o plano de pagamento, o desconto à vista, as dimensões financeiras e a guia de transferência de dinheiro por débito direto quando as faturas são criadas.  
10. Selecione o padrão de recorrência.
    * Diário – Escolha esta opção e insira o número de dias no campo Por. Por exemplo, se você inserir 15, uma fatura será gerada a cada 15 dias para esse cliente.  Semanal - Escolha essa opção e insira o número de semanas no campo Por. Por exemplo, se você inserir 2, uma fatura será gerada a cada duas semanas para esse cliente.  Mensal - Escolha essa opção e insira o número de meses no campo Por. Por exemplo, se você inserir 6, uma fatura será gerada a cada seis meses para esse cliente.  Anual - Escolha essa opção e insira o número de anos no campo Por. Por exemplo, se você inserir 2, uma fatura será gerada a cada dois anos para esse cliente.  
11. No campo Por, insira um número.


