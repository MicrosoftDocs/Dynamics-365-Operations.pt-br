---
title: Preparar um trabalho kanban de processo quando materiais não estão disponíveis para a célula de trabalho
description: Esse procedimento se concentra em preparar uns trabalhos kanban de processo embora alguns materiais não estejam disponíveis para a célula de trabalho, consequentemente é necessário escolher materiais de depósito.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f75cdbc6ce6f7e427bf266c90428d73c065eac3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576727"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>Preparar um trabalho kanban de processo quando materiais não estão disponíveis para a célula de trabalho

[!include [banner](../../includes/banner.md)]

Esse procedimento se concentra em preparar uns trabalhos kanban de processo embora alguns materiais não estejam disponíveis para a célula de trabalho, consequentemente é necessário escolher materiais de depósito. O procedimento “Preparar uns trabalhos kanban de processo quando os materiais estiverem disponíveis” é um pré-requisito para a criação deste procedimento. Esse procedimento é destinado ao operador da máquina. A empresa de dados demo usada para criar este procedimento é USMF.

1. Acesse Controle de produção > Kanban > Quadro Kanban para trabalhos de processo.
2. No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
    * Selecione a célula de trabalho 1250.  
4. Na lista, localize e selecione o PDV desejado.
    * Selecionar Kanban 000356.  
5. Na lista, localize e selecione o PDV desejado.
    * Na lista, desmarque a linha 4 ou selecione a linha 4 se você não concluiu a tarefa "Preparar um trabalho kanban de processo quando os materiais estiverem disponíveis".  
6. Alternar a expansão da seção Lista de separação.
    * Nenhum ícone de entrada no status da fonte indica que 48 ea do item P0002 não foram feitas para a célula de trabalho.  

## <a name="transfer-materials-to-work-cell"></a>Materiais de transferência para célula de trabalho
1. Alternar a expansão da seção Trabalhos de transferência.
2. Use o Filtro Rápido para filtrar o campo Número do item com o valor 'P0002'.
3. Na lista, localize e selecione o PDV desejado.
4. Clique em Iniciar.
    * Transferência em andamento  
5. Clique em Concluir.
    * O item P0002 está disponível na lista de separação para os trabalhos kanban. Isso significa que podemos preparar o kanban com todos os materiais necessários.  
6. Clique em Preparar.
    * Observe que um ícone no status do trabalho indica que o trabalho agora está pronto.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]