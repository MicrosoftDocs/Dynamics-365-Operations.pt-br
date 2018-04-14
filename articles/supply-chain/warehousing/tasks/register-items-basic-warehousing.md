--- 
title: "Registrar itens para um item básico com armazenamento habilitado usando um diário de entrada de itens"
description: "Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando “depósito básico“ no módulo de gerenciamento de estoque."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: c7148bd807ef29b0dd89204a0fbe9b8480095aba
ms.contentlocale: pt-br
ms.lasthandoff: 11/02/2017

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registrar itens para um item básico com armazenamento habilitado usando um diário de entrada de itens

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando “depósito básico“ no módulo de gerenciamento de estoque. Normalmente isso é feito por um vendedor de remessa. Você pode executar oeste procedimento na empresa USMF com dados de demonstração usando os valores de exemplo mostrados.  Se você não estiver usando USMF, você precisa ter uma ordem de compra confirmada com uma linha de ordem de compra aberta antes de dar início a este guia. O item da linha deve ser armazenado, e não deve usar grades de produto, e não deve ter dimensões de rastreamento. E o item precisa estar associado a um grupo de dimensões de armazenamento, onde o site e o depósito estão ativos.


## <a name="create-item-arrival-journal-header"></a>Criar cabeçalho de diário de entrada de itens.
1. Vá para Gerenciamento de estoque > Entradas de diário > Chegada de item > Chegada de item.
2. Clique em Novo.
3. No campo Nome, digite um valor.
    * Se você estiver usando USMF, você pode digitar WHS. Se você estiver usando outros dados, o diário cujo nome você escolheu precisará ter as seguintes propriedades: o local de separação de verificação deve ser definido como Não, e o gerenciamento de quarentena deve ser definido como Não.  
4. No campo Guia de remessa, digite um valor.
    * Este é o ID da guia de remessa da guia de remessa emitido pelo fornecedor. Adicionar um número único.  
5. No campo Número, selecione a ordem de compra.
6. Clique em OK.

## <a name="add-lines-to-item-arrival-journal"></a>Adicionar linhas ao diário de chegada de item
1. Clique em Funções.
2. Clique em Criar linhas.
    * As linhas podem ser inseridas manualmente no diário ou ser criadas automaticamente. Isso mostrará como criar essas automaticamente.  
3. Marcar ou desmarcar a caixa de seleção Iniciar quantidade.
    * Isso inicializará a quantidade nas linhas do diário com a quantidade não registrada da linha da ordem de compra.  
4. Clique em OK.

## <a name="post-the-journal"></a>Lançar o diário
1. Clique em Lançar.
2. Clique em OK.

## <a name="generate-the-product-receipt"></a>Gerar o recebimento de produtos
1. Clique em Funções.
2. Clique em Recebimento de produtos.
3. Clique em OK.


