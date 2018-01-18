---
title: Funcionalidade do call center
description: "Este tópico fornece uma visão geral da funcionalidade de vendas do call center no Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 52b3e2e78a03ac67507ee65a03e0884e5ed44678
ms.openlocfilehash: 75dc09ffc84ef8ec48f50ea410974c99aabc212e
ms.contentlocale: pt-br
ms.lasthandoff: 11/14/2017

---

# <a name="call-center-functionality"></a>Funcionalidade do call center

[!include[banner](includes/banner.md)]


Este artigo fornece uma visão geral da funcionalidade de vendas do call center no Microsoft Dynamics 365 for Retail.

O Dynamics 365 for Retail também oferece suporte a call centers como um tipo de canal de varejo. Em um call center, os trabalhadores recebem ordens de clientes pelo telefone e criam ordens de venda. A funcionalidade do call center inclui recursos criados para facilitar a obtenção de ordens por telefone e controlar o atendimento ao cliente durante todo o processo de preenchimento da ordem. Por exemplo, os trabalhadores do call center podem inserir informações de pagamento diretamente na ordem de venda, bem como podem exibir um resumo detalhado de encargos e pagamentos antes de enviar a ordem. Os trabalhadores têm opções para controlar a definição de preços e podem acessar vários dados sobre clientes, produtos e preços na página **Ordem de venda**. Além disso, os call centers aprimoraram a funcionalidade para controlar o histórico do cliente e o status da ordem. Cada call center pode ter seus próprios usuários, métodos de pagamento, grupos de preços, dimensões financeiras e modos de entrega. Você pode configurar essas opções ao criar o call center. Você também pode usar a página **Call center** para habilitar ou desabilitar os seguintes grupos de recursos exclusivos de call centers:

-   **Conclusão da ordem** – Este grupo inclui recursos relativos a pagamentos e conclusão de ordens na página **Ordem de venda**.
-   **Venda direta** – Este grupo inclui recursos relativos aos códigos fonte, scripts e solicitações de catálogo.

Após você habilitar esses recursos nas configurações do call center, eles são disponibilizados na página **Ordem de venda** para usuários associados ao call center. A maioria desses recursos exige configuração adicional antes que eles possam ser usados. Para que os usuários possam criar ordens do call center, você deve adicionar esses usuários ao call center como usuários do call center. Esta etapa habilita a configuração e a funcionalidade específicas de canal do call center. Veja alguns exemplos da funcionalidade que é disponibilizada:

-   A venda guiada fornece opções de configuração para que scripts de televendas e imagens de produtos ajudem e orientem os auxiliares de vendas quando receberem ordens.
-   As ordens só podem ser concluídas quando os auxiliares de vendas capturam pelo menos um método de pagamento.
-   Regras de venda adicional e de venda cruzada podem ser configuradas para solicitar auxiliares de vendas que promovam produtos específicos para o cliente.
-   Os auxiliares de vendas podem capturar o código de origem para o catálogo no qual um cliente faz pedidos.
-   Os auxiliares de vendas podem adicionar cupons de um varejista à ordem.
-   Os auxiliares de vendas podem vender programas de continuidade.
-   As ordens podem ser colocadas em espera, manual ou automaticamente, para indicar que a investigação adicional é necessária antes de a ordem ser processada.





