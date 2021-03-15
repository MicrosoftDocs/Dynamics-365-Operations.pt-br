---
title: Reverter status do trabalho kanban
description: Esse procedimento se concentra em reverter um status incorreto do trabalho kanban.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bc147ec517b8141b4764f67d21b4c4a2e4d6e6e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981147"
---
# <a name="revert-kanban-job-status"></a>Reverter status do trabalho kanban

[!include [banner](../../includes/banner.md)]

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
    * Você pode usar uma regra kanban alternativa quando as seguintes condições forem verdadeiras: - a estratégia de reabastecimento é a mesma para ambas as regras.  - A versão do fluxo de produção for a mesma para ambas as regras.  - O produto que for fornecido for o mesmo para ambas as regras.  - Todas as atividades downstream que estão configuradas para a última atividade das regras kanban devem ser iguais para ambas as regras.  - As mesmas dimensões de estoque fornecidas devem ser configuradas para ambas as regras.  - O status da unidade de manuseio de material deve ser Não atribuído.  - A configuração de kanbans de evento deve ser a mesma.  
    * Verifique se o novo status é Planejado.  
4. Clique em OK.
5. Na lista, desmarque a linha selecionada.
    * Selecione o mesmo trabalho.  
    * Observe que o status do trabalho para o trabalho kanban será revertido para Planejado, que é indicado por um ícone kanban vazio.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]