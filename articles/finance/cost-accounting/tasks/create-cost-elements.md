---
title: 'Criar elementos de custo  '
description: Há várias maneiras de criar elementos de custo na Contabilização de custos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87f93fd7c1c42045274d6b89847b27e93614d9a4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440487"
---
# <a name="create-cost-elements"></a>Criar elementos de custo   

[!include [banner](../../includes/banner.md)]

Há várias maneiras de criar elementos de custo na Contabilização de custos. Este procedimento mostra como criar elementos de custo importando as contas principais por meio de um conector de dados. A empresa de demonstração USMF foi usada para criar este procedimento. Este procedimento é para um recurso de Contabilização de custos que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="create-new-cost-elements"></a>Criar novos elementos de custo
1. Vá para Contabilização de custos > Dimensões > Dimensões do elemento de custo.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Conector de dados para membros de dimensões, insira ou selecione um valor.
5. No campo Descrição, digite um valor.
6. Clique em Salvar.

## <a name="configure-the-data-connector"></a>Configurar o conector de dados
1. Clique em Configurar provedor de membro de dimensão.
2. No campo Plano de contas, insira ou selecione um valor.
    * Selecione Compartilhado para usar o plano de contas compartilhado.  
3. Clique em Novo.
4. Na lista, marque a linha selecionada.
    * Você pode aplicar filtros às contas para que atendam a seus critérios.  
5. No campo Da conta principal, insira ou selecione um valor.
6. No campo Para conta principal, insira ou selecione um valor.
7. Clique em OK.

## <a name="import-main-accounts"></a>Importar contas principais
1. Clique em Importar membros da dimensão.
    * As contas principais serão importadas para a Contabilização de custos e usadas como elementos de custo.  
2. Clique em OK.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Exibir as contas importadas como elementos de custo
1. Clique em Exibir membros da dimensão.
    * Exiba as contas contábeis importadas como elementos de custo na empresa para a qual os custos possam fluir.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]