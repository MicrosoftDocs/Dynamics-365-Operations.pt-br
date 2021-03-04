---
title: Criar uma ordem de compra regida por orçamento
description: Use este procedimento para criar uma ordem de compra que seja verificada para o orçamento disponível.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 319eb0070a3677035e2a5d89744e80cd38c08d8e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422259"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Criar uma ordem de compra regida por orçamento

[!include [banner](../../includes/banner.md)]

Use este procedimento para criar uma ordem de compra que seja verificada para o orçamento disponível. Esta gravação usa os dados da empresa de demonstração USMF.


## <a name="review-the-budget-control-configuration"></a>Revise a configuração de controle de orçamento
1. Vá para Orçamento > Configuração > Controle de orçamento > Configuração de controle de orçamento.
2. Clique na guia disponível dos fundos de orçamento.
3. Clique na guia Documentos e diários.
4. Clique na guia Definir regras de controle de orçamento.
5. Clique na guia Definir os grupos orçamentários.
6. Feche a página.

## <a name="create-the-purchase-order-header"></a>Criar o cabeçalho da ordem de compra
1. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, insira ou selecione um valor.
4. Expanda a seção Geral.
5. No campo Data contábil, defina a data como '01-01-2016'.
6. Clique em OK.

## <a name="add-a-purchase-order-line"></a>Adicionar uma linha de ordem de compra
1. No campo Categoria de compras, insira ou selecione um valor.
2. Defina Quantidade como '2'.
3. No campo Unidade, insira ou selecione um valor.
4. Defina o preço unitário como "10000".
5. Clique em Financeiros.
6. Clique em Distribuir valores.
7. No campo Conta contábil, especifique o valor '601300-001-023--'.
8. Feche a página.

## <a name="perform-budget-checking"></a>Executar verificação de orçamento
1. Clique em Financeiros.
2. Clique em Executar verificação de orçamento.
3. Clique em Financeiros.
4. Clique em Erros ou avisos da verificação de orçamento.
5. Clique em Fechar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]