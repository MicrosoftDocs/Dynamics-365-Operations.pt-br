---
title: Opções de transação de ativo fixo
description: Este artigo descreve os diferentes métodos disponíveis para criar transações de ativo fixo.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: kfend
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 402679b6f1003f14f7e277a326784edaaea719d5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883348"
---
# <a name="fixed-asset-transaction-options"></a>Opções de transação de ativo fixo

[!include [banner](../includes/banner.md)]

Este artigo descreve os diferentes métodos disponíveis para criar transações de ativo fixo.

Você pode configurar ativos fixos para integração com contas a pagar, contas a receber, Compras e contabilidade. Também é possível transferir itens Gerenciamento de depósito para Ativos fixos caso você queira usar esses itens internamente.

## <a name="accounts-payable"></a>Contas a Pagar
Você pode inserir transações de ativos fixos na página Comprovante de diário. Esta página pode ser aberta na página Diário de fatura. Você também pode abrir a página Comprovante de diário na página Diário de aprovação de fatura. No campo Tipo de contrapartida, selecione Ativos fixos. Em seguida, no campo Contrapartida, selecione um número de ativo fixo. Na guia Ativos fixos, insira os valores nos campos Tipo de transação e Registro.

## <a name="accounts-receivable"></a>Contas a Receber
Você pode inserir transações de ativos fixos na página Fatura de texto livre.  Na página Fatura de texto livre, na grade de linhas Fatura, selecione um item de linha. Clique a Guia Rápida Detalhes da linha. Insira o número do ativo fixo e o registro para a transação de alienação. Na fatura de texto livre, o tipo de transação de ativo fixo é sempre Descarte - venda.

## <a name="procurement-and-sourcing"></a>Compras
Você pode inserir transações de ativos fixos na página Ordem de compra. Insira as informações necessárias para criar uma ordem de compra, clique em e em OK. Na página Ordem de compra, clique na Guia Rápida Detalhes da linha. Em, no guia Ativos fixos, insira as informações sobre o ativo fixo. 

Para lançar uma transação de aquisição para um ativo fixo existente o ativo, especifique o número do ativo fixo, se o registro, e o tipo de transação. O ativo fixo não pode ser lançado se algumas informações está ausente. Para lançar uma transação de aquisição para um novo ativo fixo, selecione a opção Novo ativo fixo? e, em seguida, selecione o grupo de ativos fixos ao qual o novo ativo será atribuído. Nenhum dos campos de ativos fixos para uma linha estará disponível se o item estiver em um grupo de modelos de estoque que usa um modelo de estoque de custo padrão. Além disso, as opções definidas na página Parâmetros de ativos fixos determinam se você poderá lançar transações de aquisição os módulos de compra. 

Quando uma ordem compra ou o diário de estoque para ativos fixos é usado para a aquisição de ativos fixos, o valor do estoque é afetado.

## <a name="general-ledger"></a>Contabilidade
Qualquer tipo de transação de ativo fixo pode ser lançado na página Diário geral. Você também pode usar diários de ativos fixos para lançar transações de ativos fixos.

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Opções para inserir tipo de transações de ativos fixos


| Tipo de transação                    | Módulo                   | Opções                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Aquisição, ajuste de aquisição | Ativos fixos             | Ativos fixos, estoque para ativos fixos   |
|                                     | Contabilidade           | Diário geral                           |
|                                     | Contas a Pagar         | Diário de fatura, diário de aprovação de faturas |
|                                     | Compras | Ordem de Compra                            |
| Depreciação                        | Ativos fixos             | Ativos fixos                              |
|                                     | Contabilidade           | Diário geral                           |
| Alienação                            | Ativos Fixos             | Ativos Fixos                              |
|                                     | Contabilidade           | Diário geral                           |
|                                     | Contas a Receber      | Fatura de texto livre                         |

O valor restante não é atualizado para os períodos de depreciação de um ativo fixo quando a linha de diário do tipo de transação de depreciação é criada manualmente ou importada por meio de uma entidade de dados. O valor restante é atualizado quando o processo de proposta de depreciação é usado para criar a linha do diário.

Para obter mais informações, consulte [Integração de ativos fixos](fixed-asset-integration.md).

O sistema evita a depreciação de lançamento no mesmo período duas vezes. Por exemplo, se dois usuários criarem propostas de depreciação separadamente para Janeiro, a depreciação do primeiro usuário será lançada no primeiro diário. Quando o segundo usuário lança a depreciação no segundo diário, o sistema verifica a data da última vez em que a depreciação foi executada e não lança a depreciação para o mesmo período uma segunda vez.

### <a name="transactions-that-require-a-different-voucher-number"></a>Transações que exigem um número de comprovante diferente

As transações de ativos fixos a seguir usarão números de comprovante diferentes:

- Uma aquisição adicional é feita em um ativo e a depreciação de "atualização" é calculada.
- Um ativo é dividido.
- Um parâmetro para calcular a depreciação na alienação é habilitado e, em seguida, o ativo é descartado.
- A data de serviço de um ativo é anterior à data de aquisição. Portanto, um ajuste de depreciação é lançado.

> [!NOTE]
> Quando inserir transações, verifique se todas as transações se aplicam ao mesmo ativo fixo. Um comprovante não será lançado se incluir mais de um ativo fixo, mesmo se o campo **Novo Comprovante** tiver sido definido como **Apenas um número de comprovante** na página **Nomes de diários** em Contabilidade. Se incluir mais de um ativo fixo no comprovante, você receberá a mensagem "Só pode haver uma transação de ativo fixo por comprovante", e não será possível lançar o comprovante.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
