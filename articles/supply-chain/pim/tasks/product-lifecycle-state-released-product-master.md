---
title: Atribuir um estado do ciclo de vida do produto a um produto mestre liberado
description: Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "309463"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Atribuir um estado do ciclo de vida do produto a um produto mestre liberado

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades. Pré-requisito: você precisará executar o guia de tarefas “Criar um novo estado do ciclo de vida do produto” primeiro para garantir que tem pelo menos um estado do ciclo de vida do produto criado antes de executar este guia de tarefas.


## <a name="find-a-released-product-master"></a>Encontre um produto mestre liberado
1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Na lista, localize e selecione o PDV desejado.

> [!NOTE]
> Um produto mestre tem o subtipo de Produto Produto mestre.  

## <a name="update-the-lifecycle-state"></a>Atualize o estado do ciclo de vida
1. Clique em Editar.
2. No campo Estado do ciclo de vida do produto, insira ou selecione um valor.
3. Clique em Salvar.
4. Clique em Sim.

> [!NOTE]
> Caso selecione Sim, todas as grades de produtos liberados relacionados, com o mesmo status original que o produto mestre liberado também serão atualizadas para o novo estado do ciclo de vida do produto. Caso selecione Não, todas as grades manterão seu estado real. As grades que tiverem um estado do ciclo de vida do produto diferente do produto mestre liberado não serão atualizadas.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>Verifique o estado do ciclo de vida das grades
1. Clique em Variantes de produtos liberados.

> [!NOTE]
> Observe que todas as grades herdaram o estado do ciclo de vida selecionado do produto mestre liberado.  

2. Na lista, marque a linha selecionada.
3. No campo Estado do ciclo de vida do produto, insira ou selecione um valor.

