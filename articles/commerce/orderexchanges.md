---
title: Configurar e processar uma troca em uma ordem de devolução
description: Este artigo explica como configurar uma troca em uma devolução no Dynamics 365 Commerce.
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
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
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845782"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Configurar e processar uma troca em uma ordem de devolução

[!include [banner](includes/banner.md)]

Em versões anteriores do Dynamics 365 Commerce, as devoluções em relação a ordens de clientes foram processadas usando o documento de ordem de devolução no Headquarters. No entanto, o documento de ordem de devolução só pode ser usado para processar os produtos que estão sendo devolvidos. Os produtos devolvidos são indicados por uma quantidade negativa nas linhas da ordem de devolução. Em contraste, as vendas são indicadas por uma quantidade positiva. Entretanto, o documento de ordem de devolução não aceita quantidades positivas. Devido a essa limitação, as versões anteriores do aplicativo não oferecem suporte aos cenários em que trocas de produto são feitas usando o documento de ordem de devolução.

A funcionalidade foi adicionada para dar suporte a cenários em que as trocas são feitas sobre ordens de devolução. O Commerce agora usa o documento da ordem de venda em vez do documento da ordem de devolução para processar esse tipo de transação.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Configure o Commerce para aceitar trocas em ordens de devolução

> [!NOTE]
> No Commerce versão 10.0.20 e posterior, um novo recurso chamado "Experiência de processamento de devolução unificado para PDV" está disponível. Se você habilitar esse recurso, as etapas de configuração a seguir não serão necessárias. **Processar devoluções como ordens de venda** se tornará uma configuração permanentemente e você não poderá alterá-la.

Siga estas etapas para configurar o sistema para oferecer suporte a trocas de ordens de devolução (se você não tiver o recurso **Experiência de processamento de devolução unificado para PDV** habilitado.

1. Acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**. Na FastTab **Ordens de cliente**, defina a opção **Processar ordens de devolução como ordens de venda** como **Sim**.
2. Execute o trabalho **Agenda de distribuição global de configuração** (**1110**).

## <a name="make-an-exchange"></a>Fazer uma troca

Depois que o sistema for configurado como descrito na seção anterior, o usuário do PDV (ponto de venda) ainda selecionará uma ordem de venda ou fatura de venda para processar uma devolução, como em versões anteriores do aplicativo. No entanto, depois que os itens de devolução forem adicionados ao carrinho, o usuário poderá adicionar novas linhas de venda ao carrinho.

Para essas novas linhas de venda, o usuário deve definir todos os atributos necessários para processar uma linha da ordem de cliente. Esses atributos incluem o método de entrega e o local de atendimento. O pagamento que é devido para a transação será um pagamento líquido das linhas da ordem de devolução e das linhas da ordem de venda. Quando o pagamento for proposto para a transação, a ordem de devolução será lançada como um documento de ordem de venda no Headquarters, e o sistema cobrará imediatamente as linhas de devolução.

Para fornecer uma melhor visibilidade dos vários valores do carrinho, três novos campos de valores foram adicionados ao carrinho. Você pode usar o designer de tela para disponibilizar esses novos campos na IU (interface de usuário) do PDV.

- **Depósito aplicado** – O valor de depósito aplicado em uma transação quando o usuário faz uma retirada por ordem de cliente. Se não houver sobreposição de depósito, e um depósito de 10% estiver configurado, o valor neste campo será de 90% do valor total da ordem do cliente.
- **Executar valor** – O valor total das linhas em que o modo de entrega foi definido como **Executar** quando a ordem de cliente foi criada ou editada, ou durante uma troca da ordem de cliente. O valor neste campo inclui impostos e encargos.
- **Valor da devolução** – O valor total das linhas que têm quantidades negativas durante a troca da ordem do cliente. O valor neste campo inclui impostos e encargos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
