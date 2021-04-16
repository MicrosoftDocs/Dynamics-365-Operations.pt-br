---
title: Configurar depreciação extra
description: Este procedimento mostra como criar uma provisão para depreciação especial e associá-la a um registro de ativos fixos.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad1b7f584d2b2a63dba5f8519ada9d89d6265e7b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815611"
---
# <a name="set-up-bonus-depreciation"></a>Configurar depreciação extra

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma provisão para depreciação especial e associá-la a um registro de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.


## <a name="create-a-special-depreciation-allowance"></a>Criar uma provisão para depreciação especial
1. Vá para Ativos fixos > Configuração > Provisão para depreciação especial.
2. Clique em Novo.
3. No campo Provisão para depreciação especial, insira um valor.
4. No campo Descrição, digite um valor.
5. No campo Porcentagem, insira um número.
    * Se uma porcentagem não foi indicada, defina um valor.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Associar uma provisão para depreciação especial a um registro de grupo de ativos fixos
1. Vá para Ativos fixos > Configuração > Grupos de ativo fixo.
2. Na lista, selecione o grupo de ativos fixos a ser associado à provisão para depreciação especial.
3. Clique em Registros.
4. Na lista, selecione o registro associado à provisão para depreciação especial.
5. Clique em Provisão para depreciação especial.
6. Clique em Novo.
7. No campo Provisão para depreciação especial, insira ou selecione um valor.
    * O padrão para a porcentagem ou o valor vem da configuração de provisão para depreciação especial.  
8. No campo Prioridade, insira um número.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]