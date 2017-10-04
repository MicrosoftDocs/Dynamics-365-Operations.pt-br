--- 
title: Transferir um ativo fixo
description: "Este guia da tarefa transfere as informações financeiras para um registro de ativo fixo de um conjunto de dimensões financeiras para um novo conjunto de dimensões financeiras."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ebde1e8bd8a87b44dd77b9050d05d6c2f4774ef2
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="transfer-a-fixed-asset"></a>Transferir um ativo fixo

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este guia da tarefa transfere as informações financeiras para um registro de ativo fixo de um conjunto de dimensões financeiras para um novo conjunto de dimensões financeiras.  Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.

1. Vá para Ativos fixos > Ativos fixos > Ativos fixos.
2. Na lista, localize e selecione o ativo fixo que você deseja transferir.
3. No Painel de Ação, clique em Ativo fixo.
4. Clique em Transferir ativos fixos.
5. No campo Transferir, insira uma data.
6. Inserir comentários para descrever a transferência.
    * A lista mostra todos os registros do ativo fixo.  
7. Marque os registros que você deseja transferir para um novo conjunto de dimensões financeiras.
    * A lista mostra os valores de dimensão financeira existentes para o registro selecionado.  
    * Selecione a dimensão financeira que você deseja atualizar para o registro de ativo fixo selecionado.  
8. No campo Dimensão financeira, clique no botão suspenso para abrir a pesquisa.
    * Definir outros valores de dimensão financeira conforme apropriado.  
    * Todos os valores de dimensão financeira são alterados quando uma transferência ocorre, seja se um valor for inserido ou estiver em branco. Por exemplo, se você inserir um valor para o campo BusinessUnit e deixar as dimensões financeiras de CostCenter e de Departamento em branco. Se a estrutura de sua conta permitir valores em branco para CostCenter e Departamento, a transferência resultaria em cada modelo de valor tendo o novo valor para BusinessUnit e um valor em branco para CostCenter e Departamento.  
9. Clique em Atualizar.
    * Você tem a oportunidade de visualizar as alterações antes de finalizar a transferência.  
    * Revise os resultados antes de transferir os registros de ativo fixo.  
10. Clique em Transferir.

