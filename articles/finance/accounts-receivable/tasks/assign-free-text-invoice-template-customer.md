---
title: Atribuir um modelo de fatura de texto livre a um cliente
description: Essa tarefa demonstra como atribuir um modelo de nota fiscal de texto livre a um cliente.
author: ShivamPandey-msft
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49074c11659ae30fd2decdb93b4721441edff2c5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780444"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Atribuir um modelo de fatura de texto livre a um cliente

[!include [banner](../../includes/banner.md)]

Essa tarefa demonstra como atribuir um modelo de nota fiscal de texto livre a um cliente. Esta tarefa usa a empresa de demonstração USMF e é direcionada para o usuário responsável por gerenciar e processar faturas A/R.

1. No **Painel de Navegação**, Acesse **Módulos > Contas a receber > Clientes > Todos os clientes**.
2. Na lista, localize e selecione o registro desejado.
3. No **Painel de Ações**, clique em **Fatura**.
4. Clique em **Faturas recorrentes**. Use esta página para atribuir modelos de fatura de texto livre para clientes e especificar quão frequentemente as faturas serão enviadas ao cliente.  
5. Clique em **Novo** para atribuir um novo modelo ao cliente.
6. No campo **Modelo**, selecione o modelo de fatura de texto livre que você deseja atribuir ao cliente.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo **Data de início de faturamento**, insira a data em que a primeira fatura será gerada.
10. Na seção **Final da recorrência**, insira uma data final recorrente.  
    Selecione uma das seguintes opções: 
    - **Nenhuma data de término** – as faturas serão geradas indefinidamente até que o modelo seja removido da conta do cliente.
    - **Data de término da cobrança** – selecione essa opção e insira a última data em que a fatura pode ser gerada.  
11. No campo **Valor cumulativo máximo**, insira o valor cumulativo máximo após o qual a geração da fatura será interrompida. Insira o valor cumulativo máximo que pode ser alcançado usando o modelo selecionado. Por exemplo, se você inserir 1.000,00 e gerar notas fiscais mensais para cada 100,00, as notas fiscais encerrarão a produção após a décima nota fiscal gerada.  
12. Na seção **Gerar faturas recorrentes usando os valores padrão de**, selecione o modelo de fatura de texto livre ou a conta do cliente. Opte por usar o modelo de fatura de texto livre ou a conta do cliente para determinar os valores padrão para o idioma, o perfil de lançamentos, o grupo de impostos, o grupo de impostos do item, o código de lista, o país/região para entrega, a moeda, as condições de pagamento, o método de pagamento, as especificações de pagamento, o plano de pagamento, o desconto à vista, as dimensões financeiras e a guia de transferência de dinheiro por débito direto quando as faturas são criadas.  
13. No campo **Padrão de recorrência**, selecione o padrão de recorrência.
    - **Diariamente** – selecione essa opção e insira o número de dias no campo Por. Por exemplo, se você inserir 15, uma fatura será gerada a cada 15 dias para esse cliente.
    - **Semanalmente** – selecione essa opção e insira o número de semanas no campo Por. Por exemplo, se você inserir 2, uma fatura será gerada a cada duas semanas para esse cliente.
    - **Mensalmente** – selecione essa opção e insira o número de meses no campo Por. Por exemplo, se você inserir 6, uma fatura será gerada a cada seis meses para esse cliente.
    - **Anualmente** – selecione essa opção e insira o número de anos no campo Por. Por exemplo, se você inserir 2, uma fatura será gerada a cada dois anos para esse cliente.  
14. No campo **Por**, insira um número.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
