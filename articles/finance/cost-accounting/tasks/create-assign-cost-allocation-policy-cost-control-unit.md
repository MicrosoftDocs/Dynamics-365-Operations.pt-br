---
title: Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos
description: Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cff10132e8007be885e9c69d97cf96c30d69f50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822846"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos

[!include [banner](../../includes/banner.md)]

Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo. Esta gravação usa os dados da empresa de demonstração USP2.


## <a name="create-a-policy"></a>Criar uma política
1. Vá para Contabilização de custos > Políticas > Políticas de alocação de custos.
2. Clique em Novo.
3. No campo Nome da política, digite um valor.
4. No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione Organização.  
5. No campo Dimensão, insira ou selecione um valor.
6. Clique em Salvar.

## <a name="create-allocation-rules"></a>Criar regras de alocação
1. Clique em Novo.
2. Na lista, marque a linha selecionada.
3. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
4. No campo Comportamento de custo, selecione 'Total'.
5. No campo Base de alocação, insira ou selecione um valor.
6. Clique em Novo.
7. Na lista, marque a linha selecionada.
8. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
9. No campo Comportamento de custo, selecione 'Total'.
10. No campo Base de alocação, insira ou selecione um valor.
11. Clique em Novo.
12. Na lista, marque a linha selecionada.
13. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
14. No campo Comportamento de custo, selecione 'Total'.
15. No campo Base de alocação, insira ou selecione um valor.
    * Continue até criar todas as regras.  
16. Clique em Salvar.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Atribua a política a uma unidade de controle de custo
1. Clique em Atribuições de políticas para unidade de controle de custo.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Válido a partir da data contábil, insira uma data.
    * As regras têm data efetiva. Um usuário ou o sistema pode expirar as regras, se uma versão mais recente for criada.  
5. No campo Unidade de controle de custo, insira ou selecione um valor.
6. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]