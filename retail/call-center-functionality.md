---
title: Funcionalidade do call center
description: "Este formulário fornece uma visão geral da funcionalidade de vendas call center no Microsoft Dynamics 365 para as operações."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf93b1f91679cdb520ead2a12a5e52108a83fbb2
ms.lasthandoff: 03/31/2017


---

# <a name="call-center-functionality"></a>Funcionalidade do call center

Este formulário fornece uma visão geral da funcionalidade de vendas call center no Microsoft Dynamics 365 para as operações.

O varejo e o comércio no Microsoft Dynamics AX dão suporte a call centers como um tipo de canal de varejo. Em um call center, os trabalhadores pegam as ordens de clientes pelo telefone e criam ordens de venda. A funcionalidade do call center inclui recursos criados para facilitar a obtenção de ordens por telefone e controlar o atendimento ao cliente durante todo o processo de preenchimento da ordem. Por exemplo, os funcionários de call center podem inserir informações de pagamento diretamente na ordem de venda, e pode exibir um resumo detalhado de encargos e de pagamento antes que enviou a ordem. Os trabalhadores têm opções para controlar a definição de preços e podem acessar vários dados sobre clientes, produtos e preços na página **Ordem de venda**. Além disso, os call centers aprimoraram a funcionalidade para controlar o histórico do cliente e o status da ordem. Cada call center pode ter seus próprios usuários, métodos de pagamento, grupos de preços, dimensões financeiras e modos de entrega. Você pode configurar essas opções ao criar o call center. Você também pode usar a página **Call center** para habilitar ou desabilitar os seguintes grupos de recursos exclusivos de call centers:

-   **Conclusão da ordem** – Este grupo inclui recursos relativos a pagamentos e conclusão de ordens na página **Ordem de venda**.
-   **Venda direta** – Este grupo inclui recursos relativos aos códigos fonte, scripts e solicitações de catálogo.

Após você habilitar esses recursos nas configurações do call center, eles são disponibilizados na página **Ordem de venda** para usuários associados ao call center. A maioria desses recursos exige configuração adicional antes que eles possam ser usados. Para que os usuários possam criar ordens do call center, você deve adicionar esses usuários ao call center como usuários do call center. Esta etapa habilita a configuração e a funcionalidade específicas de canal do call center. Veja alguns exemplos da funcionalidade que é disponibilizada:

-   A venda guiada fornece opções de configuração para que scripts de televendas e imagens de produtos ajudem e orientem auxiliares de vendas quando recebem ordens.
-   As ordens só podem ser concluídas quando os auxiliares de vendas capturam pelo menos um método de pagamento.
-   Regras de venda adicional e de venda cruzada podem ser configuradas para solicitar auxiliares de vendas que promovam produtos específicos para o cliente.
-   Os auxiliares de vendas podem capturar o código de origem para o catálogo no qual um cliente faz pedidos.
-   Os auxiliares de vendas podem adicionar cupons de um varejista à ordem.
-   Os auxiliares de vendas podem vender programas de continuidade.
-   As ordens podem ser colocadas em espera, manual ou automaticamente, para indicar que a investigação adicional é necessária antes de a ordem ser processada.



