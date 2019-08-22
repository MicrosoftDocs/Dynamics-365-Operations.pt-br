---
title: Transferir um ativo fixo
description: Este guia da tarefa transfere as informações financeiras para um registro de ativo fixo de um conjunto de dimensões financeiras para um novo conjunto de dimensões financeiras.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 167591cf160916f256e2d10f122eca312ba07639
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839728"
---
# <a name="transfer-a-fixed-asset"></a>Transferir um ativo fixo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia da tarefa transfere as informações financeiras para um registro de ativo fixo de um conjunto de dimensões financeiras para um novo conjunto de dimensões financeiras.  Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.

1. No Painel de navegação, vá para **Módulos > Ativos fixos > Ativos fixos > Ativos fixos**.
2. Na lista, localize e selecione o ativo fixo que você deseja transferir.
3. No Painel de Ação, clique em **Ativo fixo**.
4. Clique em **Transferir ativos fixos**.
5. No campo **Data de transferência**, insira uma data.
6. Inserir comentários para descrever a transferência.
    
    A lista mostra todos os registros do ativo fixo.  
7. Marque os registros que você deseja transferir para um novo conjunto de dimensões financeiras.
    * A lista mostra os valores de dimensão financeira existentes para o registro selecionado.  
    * Selecione a dimensão financeira que você deseja atualizar para o registro de ativo fixo selecionado.  
8. No campo **Dimensão financeira**, clique no botão suspenso para abrir a pesquisa.
    * Definir outros valores de dimensão financeira conforme apropriado.  
    * Todos os valores de dimensão financeira são alterados quando uma transferência ocorre, seja se um valor for inserido ou estiver em branco. Por exemplo, se você inserir um valor para o campo BusinessUnit e deixar as dimensões financeiras de CostCenter e de Departamento em branco. Se a estrutura de sua conta permitir valores em branco para CostCenter e Departamento, a transferência resultaria em cada modelo de valor tendo o novo valor para BusinessUnit e um valor em branco para CostCenter e Departamento.  
9. Clique em **Atualizar**.
    * Você tem a oportunidade de visualizar as alterações antes de finalizar a transferência.  
    * Revise os resultados antes de transferir os registros de ativo fixo.  
10. Clique em **Transferir**.

