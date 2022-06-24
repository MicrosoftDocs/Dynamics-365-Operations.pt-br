---
title: Parâmetros intercompanhia
description: Este artigo explica os parâmetros intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7a9b921c7db47fe99981438932e5587f9a18f018
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850515"
---
# <a name="intercompany-parameters"></a>Parâmetros intercompanhia

[!include [banner](../../includes/banner.md)]

Em uma organização intercompanhia, você pode configurar parâmetros que determinem como fazer negócios entre entidades legais diferentes. Esses parâmetros são determinados pelos campos que você selecionar. Você pode selecionar diferentes combinações para refletir diferentes cenários comerciais.

Os dois exemplos a seguir descrevem cenários para organizações intercompanhia, uma com dois níveis e outra com três níveis.

## <a name="example-1-two-level-intercompany-chain"></a>Exemplo 1: cadeia intercompanhia de dois níveis

A organização intercompanhia inclui as seguintes entidades legais:

- Entidade legal A – vende para clientes externos, mas não possuem estoque. Essa entidade legal compra da Entidade legal B.
- Entidade legal B – vende somente para a entidade legal A.

Ambas as entidade legais podem vender e comprar entre si.

Neste exemplo, a definição de preço da ordem de venda original, que é direcionado para o cliente externo, sempre é baseada no preço de venda. A definição de preço da ordem de venda intercompanhia e da ordem de compra intercompanhia é controlada pela definição de preço de venda ou transferência interna na ordem de venda intercompanhia da Entidade legal B.

As informações do cabeçalho da ordem são controladas na ordem de venda original para o cliente externo. Qualquer alteração na ordem de venda intercompanhia não será sincronizada com a ordem de venda original.

Na Entidade legal A, na página **Intercompanhia** para fornecedores, selecione **Políticas da ordem de compra**. Selecione os campos a seguir no grupo de campos **Ordem de venda original (entrega direta)**:

- **Imprimir guia de remessa automaticamente**
- **Lançar fatura automaticamente**
- **Imprimir fatura automaticamente**

No grupo de campos **Ordem de compra intercompanhia (entrega direta)**, selecione o seguinte campo:

- **Lançar fatura automaticamente**

No grupo **Ordem de venda original <-> Ordem de compra intercompanhia**, selecione os seguintes campos:

- **Informações do cliente**
- **Número RMA**

No grupo de campos **Ordem de compra original <-> Ordem de venda intercompanhia**, selecione os seguintes campos:

- **Informações do cliente**
- **Número RMA**
- **Nº do lote**
- **Número de série**

Na Entidade legal B, na página **Intercompanhia** para clientes, selecione **Políticas da ordem de venda**. Selecione os campos a seguir no grupo de campos **Ordem de venda intercompanhia**:

- **Numeração da ordem de venda**: **Empresa + número original**
- **Permitir atualização de resumo de documentos para cliente original**

No grupo de campos **Preços de ordem de venda intercompanhia**, selecione os seguintes campos:

- **Pesquisa de preço e desconto**
- **Permitir edição de preços**
- **Permitir edição de descontos**

No grupo de campos **Ordem de venda intercompanhia \> Ordem de compra intercompanhia**, selecione os seguintes campos:

- **Nº do lote**
- **Número de série**

## <a name="example-2-three-level-intercompany-chain"></a>Exemplo 2: cadeia intercompanhia de três níveis

A organização intercompanhia inclui as seguintes entidades legais:

- Entidade legal A – uma entidade legal de vendas que vende para clientes externos e compra da Entidade legal B.
- Entidade legal B – uma entidade legal de produção ou distribuição que não pode fornecer produtos e compra da Entidade legal C.
- Entidade legal C – uma entidade legal de produção ou distribuição que fornece produtos para a Entidade legal B.

O preço da transferência interna entre as entidades legais B e C fica a cargo da entidade legal de venda no início da cadeia. Fica também a cargo da Entidade legal A, que vende para clientes externos. Entretanto, o preço na ordem de venda original para o cliente externo sempre é baseado no preço de venda.

Os preços de todas as ordens de venda e compra intercompanhia são controlados na ordem de venda intercompanhia. Eles são controlados no início da cadeia. Portanto, a Entidade legal C, que vende para a Entidade legal B, controla o preço. O preço da ordem de venda intercompanhia é baseado no preço interno de venda ou transferência definido na Entidade legal C.

As informações do cabeçalho da ordem são controladas na ordem de venda original para o cliente externo. Qualquer alteração nas ordens intercompanhia não é sincronizada com a ordem de venda original.

Os seguintes parâmetros devem ser selecionados:

Na Entidade legal A, na página **Intercompanhia** para fornecedores, selecione **Políticas da ordem de compra**. Selecione os campos a seguir no grupo de campos **Ordem de venda original (entrega direta)**:

- **Imprimir guia de remessa automaticamente**
- **Lançar fatura automaticamente**
- **Imprimir fatura automaticamente**

No grupo de campos **Ordem de compra intercompanhia (entrega direta)**, selecione o seguinte campo:

- **Lançar fatura automaticamente**

No grupo de campos **Ordem de venda original <-> Ordem de compra intercompanhia**, selecione os seguintes campos:

- **Informações do cliente**
- **Número RMA**

No grupo de campos **Ordem de compra original <-> Ordem de venda intercompanhia**, selecione os seguintes campos:

- **Informações do cliente**
- **Número RMA**
- **Nº do lote**
- **Número de série**

Na Entidade legal B, na página **Intercompanhia** para clientes, selecione **Políticas da ordem de venda**. Selecione os campos a seguir no grupo de campos **Ordem de venda intercompanhia**:

- **Numeração da ordem de venda**: **Empresa + número original**
- **Permitir atualização de resumo de documentos para cliente original**

No grupo de campos **Ordem de venda intercompanhia \> Ordem de compra intercompanhia**, selecione os seguintes campos:

- **Nº do lote**
- **Número de série**

No grupo de campos **Lançamento de fatura do cliente intercompanhia**, selecione os seguintes campos:

- **Preço unitário igual ao preço de custo**
- **Iniciar lançamento de fatura de cliente original**

Na Entidade legal B, na página **Intercompanhia** para fornecedores, selecione **Políticas da ordem de compra**. Selecione os campos a seguir no grupo de campos **Ordem de venda original (entrega direta)**:

- **Imprimir guia de remessa automaticamente**
- **Lançar fatura automaticamente**
- **Imprimir fatura automaticamente**

No grupo de campos **Ordem de compra intercompanhia (entrega direta)**, selecione o seguinte campo:

- **Lançar fatura automaticamente**

No grupo de campos **Ordem de venda original <-> Ordem de compra intercompanhia**, selecione os seguintes campos:

- **Informações do cliente**
- **Número RMA**
- **Preço e desconto**

No grupo de campos **Ordem de compra original <-> Ordem de venda intercompanhia**, selecione os seguintes campos:

- **Informações do cliente**
- **Número RMA**
- **Nº do lote**
- **Número de série**

Na Entidade legal C, na página **Intercompanhia** para clientes, selecione **Políticas da ordem de venda**. Selecione os campos a seguir no grupo de campos **Ordem de venda intercompanhia**:

- **Numeração da ordem de venda**: **Código da sequência numérica**
- **Permitir atualização de resumo de documentos para cliente original**

No grupo de campos **Preços de ordem de venda intercompanhia**, selecione o seguinte campo:

- **Pesquisa de preço e desconto**

No grupo de campos **Lançamento de fatura do cliente intercompanhia**, selecione os seguintes campos:

- **Preço unitário igual ao preço de custo**
- **Iniciar lançamento de fatura de cliente original**

No grupo de campos **Ordem de venda original <-> Ordem de compra intercompanhia**, selecione os seguintes campos:

- **Nº do lote**
- **Número de série**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
