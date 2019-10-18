---
title: Criar e atribuir uma política de distribuição de custos para uma unidade de controle de custos
description: As regras de distribuição de custos são usadas para distribuir custos que foram contados financeiramente em um centro de custos coletivo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d040f9495c7fb36985b5f96c15ac43aa226da24
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176416"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Criar e atribuir uma política de distribuição de custos para uma unidade de controle de custos

[!include [task guide banner](../../includes/task-guide-banner.md)]

As regras de distribuição de custos são usadas para distribuir custos que foram contados financeiramente em um centro de custos coletivo. O contador de custos garante que o custo é distribuído para os centros de custos, de acordo com a base de alocação selecionada. Uma política e as regras correspondentes são atribuídas a uma unidade de controle de custo. Este guia de tarefas usa um exemplo para mostrar como criar uma política de distribuição de custos e as regras correspondentes.


## <a name="create-a-policy"></a>Criar uma política
1. Vá para Contabilização de custos > Políticas > Políticas de distribuição de custos.
2. Clique em Novo.
3. No campo Nome da política, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione Organização.  
6. No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione CDS P/L.  
7. No campo Dimensão, insira ou selecione um valor.
    * Selecione Elementos estatísticos.  
8. Clique em Salvar.

## <a name="create-rules-for-the-policy"></a>Criar regras para a política
1. Clique em Novo.
2. Na lista, marque a linha selecionada.
3. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Expanda a hierarquia para selecionar 094.  
4. No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione Outras despesas operacionais e depois 605110 Limpeza.  
5. No campo Comportamento de custo, selecione uma opção.
    * Escolha Custo fixo.  
6. No campo Base de alocação, insira ou selecione um valor.
7. Clique em Novo.
8. Na lista, marque a linha selecionada.
9. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Expanda a hierarquia para selecionar 094.  
10. No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione Outras despesas operacionais e depois 605150 Aluguel.  
11. No campo Comportamento de custo, selecione uma opção.
    * Escolha Custo fixo.  
12. No campo Base de alocação, insira ou selecione um valor.
13. Clique em Salvar.

## <a name="assign-rules-to-a-cost-control-unit"></a>Atribuir regras a uma unidade de controle de custos
1. Clique em Atribuições de políticas para unidade de controle de custo.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Válido a partir da data contábil, insira uma data.
    * Selecione 1º de setembro no ano fiscal válido.  
5. No campo Unidade de controle de custo, insira ou selecione um valor.
6. Clique em Salvar.

