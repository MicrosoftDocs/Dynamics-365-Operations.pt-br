---
title: Criar uma política de acúmulo de custo
description: Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política.
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
ms.openlocfilehash: facffeaf8d880bad01877b420197e29b6791ebbf
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841216"
---
# <a name="create-a-cost-rollup-policy"></a>Criar uma política de acúmulo de custo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política. Os dados demonstrativos utilizados na criação desse procedimento são do conjunto USP2.


## <a name="create-a-policy"></a>Criar uma política
1. Vá para Contabilização de custos > Políticas > Políticas de acúmulo de custo.
2. Clique em Novo.
3. No campo Nome da política, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione Acúmulo de custo CC.  
6. No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione Acúmulo de custo CC.  
7. Clique em Salvar.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Criar regras para a política
1. Clique em Novo.
2. Na lista, marque a linha selecionada.
3. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione 007.  
4. No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione Acúmulo de custo CE.  
5. No campo Elemento de custo secundário, insira ou selecione um valor.
    * Para este exemplo, mapeie o elemento de custo secundário CC-007 para o centro de custo.  
6. Clique em Novo.
7. Na lista, marque a linha selecionada.
8. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione 008.  
9. No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione Acúmulo de custo CE.  
10. No campo Elemento de custo secundário, insira ou selecione um valor.
    * Para este exemplo, mapeie o elemento de custo secundário CC-008 para o centro de custo.  
11. Clique em Novo.
12. Na lista, marque a linha selecionada.
13. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione 009.  
14. No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione Acúmulo de custo CE.  
15. No campo Elemento de custo secundário, insira ou selecione um valor.
    * Para este exemplo, mapeie o elemento de custo secundário CC-009 para o centro de custo.  
    * Continue até todos os centros de custos serem mapeados aos elementos de custo secundários correspondentes.  
16. Clique em Salvar.

