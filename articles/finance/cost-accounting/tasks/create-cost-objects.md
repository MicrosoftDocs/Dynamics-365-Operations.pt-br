---
title: 'Criar objetos de custos  '
description: Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo para a Contabilidade de custos por meio de um conector de dados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3d2ef7d6549bdeb3ba2afd2a594f36b47c912db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990758"
---
# <a name="create-cost-objects"></a>Criar objetos de custos   

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo para a Contabilidade de custos por meio de um conector de dados. A empresa de demonstração USMF foi usada para criar este procedimento. 


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

