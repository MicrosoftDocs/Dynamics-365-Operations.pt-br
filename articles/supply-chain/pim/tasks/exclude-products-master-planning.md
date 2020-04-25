---
title: Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre
description: Este procedimento mostra como criar um novo estado do ciclo de vida do produto que exclua os produtos do Planejamento mestre e do cálculo do nível da BOM.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 999702b9a14965271b1ed350cda752e715a22a25
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203586"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um novo estado do ciclo de vida do produto que exclua os produtos do Planejamento mestre e do cálculo do nível da BOM.


## <a name="create-an-obsolete-state"></a>Crie um estado obsoleto
1. Vá para Gerenciamento de informações de produto > Configuração > Estado do ciclo de vida do produto.
2. Clique em Novo.
3. No campo Estado, digite um valor.
4. Selecione Não no campo Está ativo para planejar.
5. No campo Descrição, digite um valor.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Associe o estado obsoleto a um produto liberado
1. Feche a página.
2. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
3. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Nome de pesquisa com um valor de 'M00'.
4. Clique em Editar.
5. Na lista, marque a linha selecionada.
6. No campo Estado do ciclo de vida do produto, insira ou selecione um valor.

