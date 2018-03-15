--- 
title: "Criar, calcular e lançar uma declaração para uma loja de varejo"
description: "Este procedimento orienta nas etapas manuais para criar, calcular e lançar um demonstrativo para uma loja."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 33ebb28196baa9ae944dbd124274b05cb587fea4
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a>Criar, calcular e lançar uma declaração para uma loja de varejo

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta nas etapas manuais para criar, calcular e lançar um demonstrativo para uma loja. Há também os trabalhos em lotes que podem ser configurados para as mesmas tarefas. As etapas para configurar e executar os trabalhos em lote podem ser encontradas em outros tópicos. Para concluir este procedimento, você deve ter transações que foram concluídas no PDV e recebidas pelo Dynamics AX. Esta gravação usa a empresa USRT nos dados de demonstração. Este procedimento pode fazer referência ao Microsoft Dynamics AX. Observe que o Dynamics AX agora se chama Microsoft Dynamics 365 for Operations.

1. Vá para Todos os espaços de trabalho > .. > Finanças da loja de varejo.
2. Clique em Novo demonstrativo.
3. No campo Número da loja, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. Clique em OK.
    * O Grupo de configuração tem as configurações que controlam que transações são incluídas no demonstrativo e como são agrupadas nas linhas do demonstrativo. Você pode abrir o grupo de configuração e alterar as configurações ou pode usar os padrões.  
    * O campo Método do demonstrativo define como as linhas do demonstrativo serão agrupadas.  
    * Selecione um membro da equipe ou um registro se você deseja calcular um demonstrativo somente para o membro da equipe ou registro específico.  
6. No campo Método de fechamento, selecione uma opção.
7. Clique em Calcular demonstrativo.
8. Clique em Sim.
    * Depois de calcular o demonstrativo, deve haver linhas criadas com os valores totais para cada método de pagamento e o método do demonstrativo que foi usado.  
    * Insira um valor contado em cada linha caso seja necessário ser inserido ou atualizado. O campo Contado será preenchido com valores das declarações de meios de pagamento feitas no PDV.  
9. Clique em Lançar demonstrativo.
10. Clique em Fechar.
11. Vá para Varejo e comércio > Canais > Finanças da loja de varejo.
12. Clique na guia Demonstrativos lançados.


