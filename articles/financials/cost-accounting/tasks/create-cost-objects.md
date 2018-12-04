--- 
title: 'Criar objetos de custos  '
description: "Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo do Dynamics 365 for Finance and Operations, edição Enterprise para a Contabilização de custos por meio de um conector de dados."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-objects"></a>Criar objetos de custos   

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo do Dynamics 365 for Finance and Operations, edição Enterprise para a Contabilização de custos por meio de um conector de dados. A empresa de demonstração USMF foi usada para criar este procedimento. Este procedimento é para um recurso de contabilização de custos que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="create-new-cost-objects"></a>Criar novos objetos de custo
1. Vá para Contabilização de custos > Dimensões > Dimensões do objeto de custo.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Conector de dados para membros de dimensões, insira ou selecione um valor.
5. No campo Descrição, digite um valor.
6. Clique em Salvar.

## <a name="configure-the-data-connector"></a>Configurar o conector de dados
1. Clique em Configurar provedor de membro de dimensão.
    * Selecione CostCenter para importar a dimensão do CostCenter para a Contabilização de custos.  
2. No campo Nome da dimensão, selecione Centro de custo.
3. Clique em OK.

## <a name="import-cost-centers"></a>Importar centros de custos
1. Clique em Importar membros da dimensão.
2. Clique em OK.

## <a name="view-the-imported-cost-centers"></a>Exibir os centros de custo importados
1. Clique em Exibir membros da dimensão.


