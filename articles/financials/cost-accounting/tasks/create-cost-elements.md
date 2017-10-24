--- 
title: 'Criar elementos de custo  '
description: "Há várias maneiras de criar elementos de custo na Contabilização de custos."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e665fc53455e457a2488f4ec28ebb5b715d90eb
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-elements"></a>Criar elementos de custo   

[!include[task guide banner](../../includes/task-guide-banner.md)]

Há várias maneiras de criar elementos de custo na Contabilização de custos. Este procedimento mostra como criar elementos de custo importando as contas principais por meio de um conector de dados. A empresa de demonstração USMF foi usada para criar este procedimento. Este procedimento é para um recurso de contabilização de custos que foi adicionado à versão 1611 do Dynamics 365 for Operations.


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


