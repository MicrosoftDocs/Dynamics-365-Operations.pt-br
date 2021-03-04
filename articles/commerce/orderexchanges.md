---
title: Configurar e processar uma troca em uma ordem de devolução
description: Este tópico explica como configurar uma troca em uma devolução no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 60d58e4194481c875c5ff3f08fc3f8e12a87caa0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114690"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Configurar e processar uma troca em uma ordem de devolução

[!include [banner](includes/banner.md)]

Em versões anteriores do Dynamics 365 Commerce, as devoluções em relação a ordens de clientes foram processadas usando o documento de ordem de devolução no Headquarters. No entanto, o documento de ordem de devolução só pode ser usado para processar os produtos que estão sendo devolvidos. Os produtos devolvidos são indicados por uma quantidade negativa nas linhas da ordem de devolução. Em contraste, as vendas são indicadas por uma quantidade positiva. Entretanto, o documento de ordem de devolução não aceita quantidades positivas. Devido a essa limitação, as versões anteriores do aplicativo não oferecem suporte aos cenários em que trocas de produto são feitas usando o documento de ordem de devolução.

A funcionalidade foi adicionada para dar suporte a cenários em que as trocas são feitas sobre ordens de devolução. O Commerce agora usa o documento da ordem de venda em vez do documento da ordem de devolução para processar esse tipo de transação.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Configure o Commerce para aceitar trocas em ordens de devolução

Execute as etapas a seguir para configurar o sistema para que aceite trocas em ordens de devolução.

1. Vá para **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**. Na FastTab **Ordens de cliente**, defina a opção **Processar ordens de devolução como ordens de venda** como **Sim**.
2. Execute o trabalho **Agenda de distribuição global de configuração** (**1110**).

## <a name="make-an-exchange"></a>Fazer uma troca

Depois que o sistema for configurado como descrito na seção anterior, o usuário do PDV (ponto de venda) ainda selecionará uma ordem de venda ou fatura de venda para processar uma devolução, como em versões anteriores do aplicativo. No entanto, depois que os itens de devolução forem adicionados ao carrinho, o usuário poderá adicionar novas linhas de venda ao carrinho.

Para essas novas linhas de venda, o usuário deve definir todos os atributos necessários para processar uma linha da ordem de cliente. Esses atributos incluem o método de entrega e o local de atendimento. O pagamento que é devido para a transação será um pagamento líquido das linhas da ordem de devolução e das linhas da ordem de venda. Quando o pagamento for proposto para a transação, a ordem de devolução será lançada como um documento de ordem de venda no Headquarters, e o sistema cobrará imediatamente as linhas de devolução.

Para fornecer uma melhor visibilidade dos vários valores do carrinho, três novos campos de valores foram adicionados ao carrinho. Você pode usar o designer de tela para disponibilizar esses novos campos na IU (interface de usuário) do POS.

- **Depósito aplicado** – O valor de depósito aplicado em uma transação quando o usuário faz uma retirada por ordem de cliente. Se não houver sobreposição de depósito, e um depósito de 10% estiver configurado, o valor neste campo será de 90% do valor total da ordem do cliente.
- **Executar valor** – O valor total das linhas em que o modo de entrega foi definido como **Executar** quando a ordem de cliente foi criada ou editada, ou durante uma troca da ordem de cliente. O valor neste campo inclui impostos e encargos.
- **Valor da devolução** – O valor total das linhas que têm quantidades negativas durante a troca da ordem do cliente. O valor neste campo inclui impostos e encargos.
