---
title: Criar uma política de acúmulo de custo
description: Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50a50dc359dc4c2741ac4d280a9f97c6a7f2c259
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810004"
---
# <a name="create-a-cost-rollup-policy"></a>Criar uma política de acúmulo de custo

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]