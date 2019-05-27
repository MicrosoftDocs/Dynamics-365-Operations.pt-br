---
title: Estabelecer taxas de pagamento de clientes
description: Criar taxas de pagamento para pagamentos de clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5acb202d46ef39376a01ca592f60926786d11186
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572965"
---
# <a name="establish-customer-payment-fees"></a>Estabelecer taxas de pagamento de clientes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Criar taxas de pagamento para pagamentos de clientes.

Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a receber > Configurar pagamentos > Taxa de pagamento
2. Clique em Novo.
3. No campo ID de taxa, insira um ID de taxa.
    * Exibe a ID de taxa em diários de pagamentos, o que o tornam descritivo para compreender a taxa que será avaliada.  
4. No campo Nome, insira um Nome de taxa.
5. No campo Descrição de taxa, insira uma descrição para a taxa.
6. Selecione se a taxa será cobrada do cliente ou em uma conta contábil.
    * Se o cliente for avaliado pela taxa, selecione Cliente. Se a taxa for avaliada por sua organização como uma despesa, selecione o Razão. Para essa tarefa, selecione Cliente.  
7. Selecione o tipo de diário que pode usar a taxa de pagamento.
    * Se essas taxas são usadas para pagamentos de cliente, o tipo de diário será provavelmente Pagamento de cliente.  
8. Clique em Salvar.
9. Clique em Configuração de taxa de pagamento.
    * A configuração da taxa de pagamento é usada para definir os critérios para a taxa de pagamento que será avaliada.  Por exemplo, você pode definir que a taxa será calculada se a conta bancária for USMF OPER, e o método de pagamento é cheque.  
10. Selecione Tabela, Grupo ou Tudo para definir contas bancárias que serão avaliadas por essa taxa.
    * Se você selecionar Tudo, todas as contas bancárias podem ser avaliadas por essa taxa.  Se você selecionar Tabela, apenas a conta bancária que você seleciona pode ser cobrada por essa taxa. Se você selecionar Grupo, somente as contas bancárias no grupo de bancos selecionado podem ser avaliadas por essa taxa.  
11. Selecione um grupo de bancos ou uma conta bancária.
    * Se você selecionou Tabela, a pesquisa exibirá contas bancárias. Se você selecionou Grupo, a pesquisa exibirá grupos bancários.  
12. Na lista, clique no link na linha selecionada.
13. Selecione o Método de pagamento a ser usado por essa taxa.
    * Por exemplo, você pode classificar uma taxa para os clientes se enviar pagamentos como um cheque, em vez de como um pagamento eletrônico.  
14. Na lista, localize e selecione o PDV desejado.
15. Se relevante, insira uma moeda do pagamento.
    * A moeda de pagamento é usada como critérios adicionais para se a taxa que será avaliada.  Por exemplo, seu banco pode cobrar uma taxa adicional para pagamentos recebidos na moeda USD, desde que transacionem normalmente somente na moeda de Euro.  
16. Selecione se a taxa será uma porcentagem, um valor ou um intervalo.
17. Insira a porcentagem ou o valor da taxa.
    * Se o campo Porcentagem/Valor for porcentagem, o valor fornecido aqui será uma porcentagem. Se o campo Porcentagem/Valor for Valor, o valor fornecido aqui será um valor. Se o campo Porcentagem/Valor for intervalo, use a guia Intervalo para definir as camadas.  
18. No campo Moeda da taxa, selecione a moeda da taxa.
    * Esta é a moeda na qual a taxa será criada.  
19. Clique em Salvar.

