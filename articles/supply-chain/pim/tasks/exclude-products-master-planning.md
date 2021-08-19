---
title: Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre
description: Este procedimento mostra como criar um novo estado do ciclo de vida do produto que exclua os produtos do Planejamento mestre e do cálculo do nível da BOM.
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
ms.openlocfilehash: 1050aeb3f7acf9902f86aac60dae7fe89bbd847016c95e2acce3e539812c7023
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772511"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um novo estado do ciclo de vida do produto que exclua os produtos do Planejamento mestre e do cálculo do nível da BOM.


## <a name="create-an-obsolete-state"></a>Crie um estado obsoleto
1. Acesse Gerenciamento de informações de produto > Configuração > Estado do ciclo de vida do produto.
2. Clique em Novo.
3. No campo Estado, digite um valor.
4. Selecione Não no campo Está ativo para planejar.
5. No campo Descrição, digite um valor.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Associe o estado obsoleto a um produto liberado
1. Feche a página.
2. Acesse Gerenciamento de informações do produto > Produtos > Produtos liberados.
3. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Nome de pesquisa com um valor de 'M00'.
4. Clique em Editar.
5. Na lista, marque a linha selecionada.
6. No campo Estado do ciclo de vida do produto, insira ou selecione um valor.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]