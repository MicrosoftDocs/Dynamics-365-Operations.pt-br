--- 
title: "Trabalhos de produção sequencial para manufatura de processos"
description: Este procedimento usa produtos de pintura como um exemplo para mostrar como sequenciar ordens planejadas de acordo com a prioridade de cor e de tamanho de pacote.
author: ChristianRytt
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 87e35de4744a0728cd41192b4afc750b575a1324
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Trabalhos de produção sequencial para manufatura de processos

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento usa produtos de pintura como um exemplo para mostrar como sequenciar ordens planejadas de acordo com a prioridade de cor e de tamanho de pacote. A empresa de dados demo usada para criar este procedimento é USPI. Esse procedimento é criado para o planejador de produção.


## <a name="run-master-planning-for-uspi"></a>Executar planejamento mestre para USPI
1. Vá para Planejamento mestre > Planejamento mestre > Executar > Planejamento mestre.
2. No campo Plano mestre, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
    * Selecionar MasterPlan.  
4. Clique em OK.
    * Isso inicia o planejamento mestre, incluindo o processo de sequência. Esse processo pode levar alguns minutos.  

## <a name="view-planned-orders-for-the-paint-products"></a>Exibir ordens planejadas para os produtos de pintura
1. Vá para Planejamento mestre > Planejamento mestre > Ordens planejadas.
2. Expanda a FactBox detalhes do item.
3. Expanda a FactBox detalhes da programação.
4. No campo Plano, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o PDV desejado.
    * Selecionar MasterPlan.  
6. Na lista, clique no link na linha selecionada.
7. Use o Filtro Rápido para filtrar o campo Número do item com o valor 'P300'.
    * Desbloquear para rolar à direita para ver a data da ordem e a data de entrega. Observe que esses itens têm uma data de pedido de Hoje e as datas de entrega para as ordens planejadas não estão em sequência após a prioridade de cor e tamanho de pacote, como exibido no nome do produto. Você pode passar o mouse sobre um número de item para ver o nome do produto e a prioridade.  

## <a name="sequence-planned-orders-for-paint"></a>Ordens planejadas em sequência para pintura
1. Feche a página.
2. Vá para Planejamento mestre > Planejamento mestre > Ordens planejadas sequenciais.
3. Expanda a FactBox detalhes do item.
4. Expanda a FactBox detalhes da programação.
    * Observação: Aqui você verá que a data de início/hora das ordens planejadas é arranjada na sequência de acordo com a cor e tamanho da embalagem dentro de um período de classificação de 28 dias. Os períodos são definidos por um número no campo Campanha. O formulário de ordem planejada sequenciado atua como o formulário de ordem planejada típico, e o planejador de produção pode confirmar ordens planejadas aqui.  
5. Marcar todas as linhas.
6. Clique em Aceitar.
    * Isso atualizará as ordens planejadas com a ação selecionada da sequência de Adiar ou Avançar.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Verifique a sequência das ordens planejadas
1. Feche a página.
2. Vá para Planejamento mestre > Planejamento mestre > Ordens planejadas.
3. Expanda a FactBox detalhes do item.
4. Expanda a FactBox detalhes da programação.
5. No campo Plano, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
    * Selecionar MasterPlan.  
7. Na lista, clique no link na linha selecionada.
8. Use o Filtro Rápido para filtrar o campo Número do item com o valor 'P300'.
    * Observe que as ordens são arranjadas agora na sequência de acordo com a prioridade de cor e tamanho e as ordens planejadas se iniciam na data de ordem mais antiga e data de entrega. Validar a coluna Data da ordem ou Data de início no Quadro de Fatos de detalhes do plano.  


