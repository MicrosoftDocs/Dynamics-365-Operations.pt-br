---
title: Registrar itens para um item básico com armazenamento habilitado usando um diário de entrada de itens
description: Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver utilizando "depósito básico" no módulo de gerenciamento de estoque.
author: Mirzaab
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76dd2bfd57db7dfd5c2baf59a864e59a509a64e0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577783"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Registrar itens para um item básico com armazenamento habilitado usando um diário de entrada de itens

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver utilizando "depósito básico" no módulo de gerenciamento de estoque. Normalmente isso é feito por um vendedor de remessa. Você pode executar oeste procedimento na empresa USMF com dados de demonstração usando os valores de exemplo mostrados.  Se você não estiver usando USMF, você precisa ter uma ordem de compra confirmada com uma linha de ordem de compra aberta antes de dar início a este guia. O item na linha deve ser estocado. E o item precisa estar associado a um grupo de dimensões de armazenamento, onde o site e o depósito estão ativos.


## <a name="create-item-arrival-journal-header"></a>Criar cabeçalho de diário de entrada de itens.
1. Acesse Gerenciamento de estoque > Entradas de diário > Chegada de item > Chegada de item.
2. Clique em Novo.
3. No campo Nome, digite um valor.
    * Se você estiver usando USMF, você pode digitar WHS. Se você estiver usando outros dados, o diário que você escolher o nome precisará ter as seguintes propriedades: Verificar local de separação deve estar definida como Não e Gerenciamento de quarentena deve estar definido como Não.  
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]