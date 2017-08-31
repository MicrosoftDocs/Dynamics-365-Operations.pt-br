--- 
title: Reverter status do trabalho kanban
description: Esse procedimento se concentra em reverter um status incorreto do trabalho kanban.
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 00b6ae872e60a322c994420ab69236abef7fb312
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="revert-kanban-job-status"></a>Reverter status do trabalho kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento se concentra em reverter um status incorreto do trabalho kanban. Isso é útil, se o operador da máquina atualiza o trabalho errado ou define o status errado por engano. Nesse procedimento, um trabalho kanban é registrado como preparado por engano, e o status é revertido. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento se destina ao supervisor de loja ou ao operador de máquina que trabalha em uma empresa de lean manufacturing.


## <a name="open-process-board-for-the-work-cell"></a>Abra o quadro de processo para a célula de trabalho
1. Vá para o quadro kanban para processar trabalhos.
2. No campo Célula de trabalho, insira ou selecione um valor.
    * Selecione a célula de trabalho 1260.  

## <a name="prepare-kanban-job"></a>Prepare o trabalho kanban
1. Clique em Preparar.
    * Se você não puder clicar em Preparar porque está esmaecida, certifique-se de que o trabalho kanban selecionado tem o status Planejado, que é indicado pelo ícone vazio de kanban. Se a opção Preparar falhar, certifique-se de que todos os materiais da Lista de separação estarão disponíveis.  
2. Na lista, selecione o trabalho preparado.
    * Selecione o primeiro trabalho que você acabou de preparar.  
    * Observe que os status dos trabalhos são preparados, que é indicado com um triângulo no ícone do kanban.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Reverta o status do trabalho kanban preparado
1. Na lista, marque a linha selecionada.
    * Selecione o primeiro trabalho que você preparou.  
2. No painel de Ação, clique em Fabricar.
3. Clique em Reverter status.
    * Você pode usar uma regra kanban alternativa quando as seguintes condições forem verdadeiras: - a estratégia de reabastecimento é a mesma para ambas as regras.  - A versão do fluxo de produção for a mesma para ambas as regras.  - O produto que for fornecido for o mesmo para ambas as regras.  - Todas as atividades downstream que estão configuradas para a última atividade das regras kanban devem ser iguais para ambas as regras.  - As mesmas dimensões de estoque fornecidas devem ser configuradas para ambas as regras.  - O status da unidade de manuseio de material Não deve ser atribuído.  - A configuração de kanbans de evento deve ser a mesma.  
    * Verifique se o novo status é Planejado.  
4. Clique em OK.
5. Na lista, desmarque a linha selecionada.
    * Selecione o mesmo trabalho.  
    * Observe que o status do trabalho para o trabalho kanban será revertido para Planejado, que é indicado por um ícone kanban vazio.  


