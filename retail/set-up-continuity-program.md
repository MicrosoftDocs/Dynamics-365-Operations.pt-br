---
title: Configurar um programa da continuidade para um call center
description: Este artigo descreve como configurar um programa de continuidade para um call center.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: e9103d5ffa0998e3bf072bb87db261dac6e798d2
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="set-up-a-continuity-program-for-a-call-center"></a>Configurar um programa da continuidade para um call center

[!include[banner](includes/banner.md)]


Este artigo descreve como configurar um programa de continuidade para um call center.

Em um programa de continuidade, que também é conhecido como um programa de ordem recorrente, os clientes recebem remessas regulares de produtos de acordo com uma agenda predefinida. Cada remessa pode conter um produto diferente, como no caso de um clube de livro do mês, ou o mesmo produto pode ser enviado repetidamente. Para configurar um programa de continuidade, deve concluir as seguintes tarefas.

1.  Defina os parâmetros de continuidade na página **Parâmetros do call center**.
2.  Crie um programa de continuidade que especifica detalhes como o plano de pagamento, a hora das remessas e se o faturamento será adiantado. Você também deve adicionar uma lista de produtos que estejam incluídos no programa de continuidade. Cada produto recebe um número de identificação de evento que é atribuído sequencialmente, começando com 1. As identificações de evento determinam a ordem em que os produtos são enviados.
    -   Se os clientes receberem um produto diferente em cada remessa, os produtos são enviados na ordem sequencial, com base nas IDs de evento, e começando com o evento atual.
    -   Se clientes receberem o mesmo produto em cada remessa, a lista conterá apenas um produto com uma ID do evento. O mesmo evento ocorre repetidamente. Você pode especificar quantas vezes cada evento será repetido.

3.  Crie um produto pai que representa o programa de continuidade que você criou na tarefa 2. Se você adicionar este produto a uma ordem de venda, a página **Continuidade** abrirá. Em seguida, você poderá usar essa página para criar a ordem de continuidade. O produto pai não especifica os produtos individuais que o cliente recebe em cada remessa.

Depois de configurar um programa de continuidade conforme descrito acima, você poderá criar uma ordem de continuidade para um cliente. Talvez também seja necessário realizar as tarefas de manutenção adicionais.

-   **Atualizar o período de evento atual de continuidade** – Configure um trabalho em lotes que avisa o sistema qual é o período do evento atual.
-   **Criar ordens filhas de continuidade** – Crie ordens filhas a partir da ordem de continuidade pai.
-   **Processar pagamentos de continuidade** – Processar cobrança e notificações para pagamentos associados a ordens de venda de continuidade.
-   **Estender linhas da continuidade** (se necessário) – Estenda o número de vezes em que um evento de continuidade possa ser repetido. A repetição de remessas poderá se estender além de limite foi definido no campo **Limite da repetição de continuidade** nos parâmetros de call center.
-   **Executar uma atualização de continuidade** (se necessário) – Sincronize alterações entre o programa de continuidade e as ordens de venda pai de continuidade.
-   **Fechar linhas e ordens pai de continuidade** – Fecha as ordens de continuidade.





