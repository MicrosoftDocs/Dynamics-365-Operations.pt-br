---
title: Configurar grupos de ativos fixos
description: Este procedimento mostra como criar um novo grupo de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48784ef4eb12a4a1cae3387e3a45afdf34f2a0fd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546423"
---
# <a name="set-up-fixed-asset-groups"></a>Configurar grupos de ativos fixos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um novo grupo de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.

1. Vá para Ativos fixos > Configuração > Grupos de ativo fixo.
2. Clique em Novo.
3. No campo grupo de ativo fixo, digite um valor.
4. No campo Nome, digite um valor.
    * Os ativos fixos e o código da sequência numérica de Autonumber no grupo de ativos fixos substituirão as configurações nos parâmetros de ativos fixos. Você pode alterá-lo aqui se os ativos no grupo de ativos fixos forem diferentes da numeração de outros grupos.  
5. Clique em Registros.
6. No campo Livro, insira ou selecione um valor.
    * Como o campo Calcular depreciação é definido como Sim, o registro do ativo será incluído nas propostas de depreciação. Se Calcular a depreciação for definido como Não, o ativo não será depreciado automaticamente.  
7. Defina a vida útil do ativo fixo, em anos.
    * Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.  
8. No campo Convenção de depreciação, selecione uma opção.
9. Feche a página.

