--- 
title: Definir taxas de pagamento de fornecedor
description: Configure taxas de pagamento de fornecedor.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 844badb3b3037df8c4f22be558f01ea3dbf37f9d
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="define-vendor-payment-fees"></a>Definir taxas de pagamento de fornecedor

[!include[task guide banner](../../includes/task-guide-banner.md)]

Configure taxas de pagamento de fornecedor. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a pagar > Configurar pagamento > Taxa de pagamento.
2. Clique em Novo.
3. No campo ID da taxa, digite um valor.
    * A ID de taxa deve descrever quando essa taxa será usada, como "EFT_Fee".  
4. No campo Nome, digite um valor.
5. No campo Descrição de taxa, digite um valor.
    * Adicione uma descrição para fornecer mais detalhes sobre quando a taxa será cobrada.  
6. No campo Encargo, selecione Fornecedor ou Razão.
    * A razão é usada quando a taxa será cobrada por sua organização.  O fornecedor é usado quando a taxa for avaliada ao fornecedor.  
7. Insira uma conta principal onde a taxa será cobrada.
    * Esta opção está disponível apenas quando selecionar a opção Razão como Encargo.  
8. Selecione o diário em que a taxa pode ser usada. 
    * Para uma taxa de pagamento de fornecedor, você selecionaria o diário de 'Pagamento fornecedor'.  
9. Clique em Salvar.
10. Clique em Configuração de taxa de pagamento.
    * Continue com a configuração da taxa de pagamento para definir quando a taxa deverá ser padronizada no diário selecionado.  
11. Selecione Tabela, Grupo ou Tudo.
    * Ela é usada para selecionar uma única conta bancária, Grupo é usado para selecionar um grupo bancário, e Tudo é usado como configuração de taxa para todas as contas bancárias  
12. Selecione um grupo de bancos ou uma conta bancária.
    * A consulta mostrará o grupo de bancos se você selecionou Grupo, contas bancárias e mostrará se você selecionou Tabela.  
13. Selecione o método de pagamento a ser usado por essa taxa.
14. Selecionar a especificação de pagamento para o método de pagamento selecionado.
    * A especificação de pagamento é usada com métodos de transferência de fundo eletrônico de pagamento.  
15. Selecione se a taxa é uma porcentagem, um valor ou um intervalo.
16. Inserir o percentual do valor da taxa.
    * Se a taxa for uma porcentagem, insira a porcentagem. Se a taxa for um valor, insira o valor da taxa. Se a taxa for um intervalo, use a guia Intervalo definida como as taxas estratificadas.  
17. No campo Moeda da taxa, selecione a moeda na qual a taxa será avaliada.
    * Esta moeda é para a taxa. A moeda do pagamento é usada para definir quando a regra de taxa deverá ser cobrada com base na moeda do pagamento. Por exemplo, seu banco pode cobrar uma taxa quando um pagamento é efetuado em Euro, mas todos pagamentos restantes não são avaliados por uma taxa.  
18. Clique em Salvar.


