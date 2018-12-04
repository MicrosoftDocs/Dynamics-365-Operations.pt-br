---
title: "Opções de transações de ativo fixo"
description: "Este artigo descreve os métodos diferentes disponíveis para criar transações de ativo fixo."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 18352ad921c2e2d110a7535f979272685105662f
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-asset-transaction-options"></a>Opções de transações de ativo fixo

[!include [banner](../includes/banner.md)]

Este artigo descreve os métodos diferentes disponíveis para criar transações de ativo fixo.

Você pode configurar ativos fixos para integração com contas a pagar, contas a receber, Compras e contabilidade. Também é possível transferir itens Gerenciamento de depósito para Ativos fixos caso você queira usar esses itens internamente.

## <a name="accounts-payable"></a>Contas a Pagar
Você pode inserir transações de ativos fixos na página Comprovante de diário. Esta página pode ser aberta na página Diário de fatura. Você também pode abrir a página Comprovante de diário na página Diário de aprovação de fatura. No campo Tipo de contrapartida, selecione Ativos fixos. Em seguida, no campo Contrapartida, selecione um número de ativo fixo. Na guia Ativos fixos, insira os valores nos campos Tipo de transação e Registro.

## <a name="accounts-receivable"></a>Contas a Receber
Você pode inserir transações de ativos fixos na página Fatura de texto livre.  Na página Fatura de texto livre, na grade de linhas Fatura, selecione um item de linha. Clique a Guia Rápida Detalhes da linha. Insira o número do ativo fixo e o registro para a transação de alienação. Na fatura de texto livre, o tipo de transação de ativo fixo é sempre Descarte - venda.

## <a name="procurement-and-sourcing"></a>Compras
Você pode inserir transações de ativos fixos na página Ordem de compra. ) Insira as informações necessárias para criar uma ordem de compra, clique em e em OK. Na página Ordem de compra, clique na Guia Rápida Detalhes da linha. Em, no guia Ativos fixos, insira as informações sobre o ativo fixo. 

Para lançar uma transação de aquisição para um ativo fixo existente o ativo, especifique o número do ativo fixo, se o registro, e o tipo de transação. O ativo fixo não pode ser lançado se algumas informações está ausente. Para lançar uma transação de aquisição para um novo ativo fixo, selecione a opção Novo ativo fixo? e, em seguida, selecione o grupo de ativos fixos ao qual o novo ativo será atribuído. Nenhum dos campos de ativos fixos para uma linha estará disponível se o item estiver em um grupo de modelos de estoque que usa um modelo de estoque de custo padrão. Além disso, as opções definidas na página Parâmetros de ativos fixos determinam se você poderá lançar transações de aquisição os módulos de compra. 

Quando uma ordem compra ou o diário de estoque para ativos fixos é usado para a aquisição de ativos fixos, o valor do estoque é afetado.

## <a name="general-ledger"></a>Contabilidade
Qualquer tipo de transação de ativo fixo pode ser lançado na página Diário geral. Você também pode usar diários de ativos fixos para lançar transações de ativos fixos.

## <a name="options-for-entering-fixed-asset-transaction-types"></a>Opções para inserir tipo de transações de ativos fixos


| Tipo de transação                    | Módulo                   | Opções                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Aquisição, ajuste de aquisição | Ativos fixos             | Ativos fixos, estoque para ativos fixos   |
|                                     | Contabilidade           | Diário geral                           |
|                                     | Contas a Pagar         | Diário de fatura, diário de aprovação de faturas |
|                                     | Compras | Ordem de Compra                            |
| Depreciação                        | Ativos fixos             | Ativos fixos                              |
|                                     | Contabilidade           | Diário geral                           |
| Alienação                            | Ativos Fixos             | Ativos Fixos                              |
| ** **                               | Contabilidade           | Diário geral                           |
| ** **                               | Contas a Receber      | Fatura de texto livre                         |



Para obter mais informações, consulte [Integração de ativos fixos](fixed-asset-integration.md).




