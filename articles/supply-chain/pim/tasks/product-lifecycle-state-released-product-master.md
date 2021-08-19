---
title: Atribuir um estado do ciclo de vida do produto a um produto mestre liberado
description: Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62078025623a0cfc1ed6797c84907c7872dfaf38095855240b306e08f3decca7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716507"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Atribuir um estado do ciclo de vida do produto a um produto mestre liberado

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades. Pré-requisito: você precisará executar o guia de tarefas “Criar um novo estado do ciclo de vida do produto” primeiro para garantir que tem pelo menos um estado do ciclo de vida do produto criado antes de executar este guia de tarefas.


## <a name="find-a-released-product-master"></a>Encontre um produto mestre liberado
1. Acesse Gerenciamento de informações do produto > Produtos > Produtos liberados.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]