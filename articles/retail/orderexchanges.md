---
title: Configurar e processar uma troca em uma ordem de devolução
description: Este tópico explica como configurar uma troca em uma devolução no Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 45b628376a483d3d639e5c018dd93570ed8ce7af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "301903"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Configurar e processar uma troca em uma ordem de devolução

[!include [banner](includes/banner.md)]

Em versões anteriores do Microsoft Dynamics 365 for Retail, as devoluções de ordens de clientes eram processadas usando o documento de ordem de devolução no Retail Headquarters. Entretanto, o documento de ordem de devolução pode ser usado para processar somente os produtos que estão sendo devolvidos. Os produtos devolvidos são indicados por uma quantidade negativa nas linhas da ordem de devolução. Em contraste, as vendas são indicadas por uma quantidade positiva. Entretanto, o documento de ordem de devolução não suporta quantidades positivas. Devido a essa limitação, versões anteriores do Retail não oferecem suporte aos cenários em que trocas de produto são feitas usando o documento de ordem de devolução.

Entretanto, a funcionalidade foi adicionada para dar suporte a cenários em que as trocas são feitas sobre ordens de devolução. O Retail agora usa o documento da ordem de venda em vez do documento da ordem de devolução para processar esses tipos de transações.

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a>Configure o Retail para oferecer suporte para trocas sobre ordens de devolução

Siga as etapas a seguir para configurar o sistema para dar suporte a trocas sobre ordens de devolução.

1. Vá para **Varejo \> Configuração da sede \> Parâmetros \> Parâmetros de varejo**. Na FastTab **Ordens de cliente**, defina a opção **Processar ordens de devolução como ordens de venda** como **Sim**.
2. Execute o trabalho **Agenda de distribuição global de configuração** (**1110**).

## <a name="make-an-exchange"></a>Fazer uma troca

Depois que o sistema for configurado como descrito na seção anterior, o usuário do PDV (ponto de venda) ainda selecionará uma ordem de venda ou fatura de venda para processar uma devolução, como em versões anteriores do Retail. No entanto, depois que os itens de devolução forem adicionados ao carrinho, o usuário poderá adicionar novas linhas de venda ao carrinho.

Para essas novas linhas de venda, o usuário deve definir todos os atributos necessários para processar uma linha da ordem de cliente. Esses atributos incluem o método de entrega e o local de atendimento. O pagamento que é devido para a transação será um pagamento líquido das linhas da ordem de devolução e das linhas da ordem de venda. Quando o pagamento for proposto para a transação, a ordem de devolução será lançada como um documento de ordem de venda no Retail Headquarters, e o sistema vai faturar imediatamente as linhas de devolução.

Para fornecer uma melhor visibilidade dos vários valores do carrinho, três novos campos de valores foram adicionados ao carrinho. Você pode usar o designer de tela para disponibilizar esses novos campos na IU (interface de usuário) do POS.

- **Depósito aplicado** – O valor de depósito aplicado em uma transação quando o usuário faz uma retirada por ordem de cliente. Se não houver sobreposição de depósito, e um depósito de 10% estiver configurado, o valor neste campo será de 90% do valor total da ordem do cliente.
- **Executar valor** – O valor total das linhas em que o modo de entrega foi definido como **Executar** quando a ordem de cliente foi criada ou editada, ou durante uma troca da ordem de cliente. O valor neste campo inclui impostos e encargos.
- **Valor da devolução** – O valor total das linhas que têm quantidades negativas durante a troca da ordem do cliente. O valor neste campo inclui impostos e encargos.
