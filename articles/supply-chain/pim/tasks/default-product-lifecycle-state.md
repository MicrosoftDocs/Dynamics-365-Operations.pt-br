---
title: Criar um estado do ciclo de vida do produto padrão
description: Este procedimento mostra como criar um estado do ciclo de vida do produto padrão, bem como associar o estado padrão com os produtos liberados.
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
ms.openlocfilehash: b62d47f52da7f9e18bce401578a5e2a629ac5eb8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818124"
---
# <a name="create-a-default-product-lifecycle-state"></a>Criar um estado do ciclo de vida do produto padrão

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um estado do ciclo de vida do produto padrão, bem como associar o estado padrão com os produtos liberados.


## <a name="create-a-default-lifecycle-state"></a>Crie um estado do ciclo de vida padrão
1. Vá para Gerenciamento de informações de produto > Configuração > Estado do ciclo de vida do produto.
2. Clique em Novo.
3. No campo Estado, digite um valor.
4. Selecione Sim no campo Padrão quando liberado para entidade legal.
5. No campo Descrição, digite um valor.
6. Selecione Não no campo Está ativo para planejar.

> [!NOTE]
> Caso um novo produto liberado não deva ser incluído no Planejamento mestre, selecione Não. Caso deva ser incluído no Planejamento mestre, deixe o controle em seu valor padrão Sim.  

## <a name="create-a-new-released-product"></a>Crie um novo produto liberado
1. Feche a página.
2. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
3. Clique em Novo.
4. No campo Número do produto, digite um valor.
5. No campo Nome do produto, digite um valor.
6. No campo Nome da pesquisa, digite um valor.
7. No campo Grupo de modelos do item, insira ou selecione um valor.
8. No campo Grupo de itens, insira ou selecione um valor.
9. No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.
10. No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.
11. Clique em OK.

> [!NOTE]
> O estado do ciclo de vida do produto padrão é uma definição global.  

## <a name="change-the-product-to-an-active-state"></a>Altere o produto para um estado ativo
1. No campo Estado do ciclo de vida do produto, insira ou selecione um valor.

> [!NOTE]
> Suponha que você tenha configurado um estado ativo, agora você pode selecioná-lo para permitir que o produto seja usado no Planejamento mestre e no cálculo do nível da BOM. Obviamente, isso só faz sentido se todos os detalhes do produto que são necessários para o planejamento consistente forem especificados.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]