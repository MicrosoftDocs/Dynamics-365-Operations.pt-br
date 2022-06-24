---
title: Alterar ordens intercompanhia
description: Este artigo explica a funcionalidade de alteração de ordens intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f139678fbb59b9132ece1ab758e141ec7cdb7a19
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852176"
---
# <a name="change-intercompany-orders"></a>Alterar ordens intercompanhia

[!include [banner](../../includes/banner.md)]

Se você alterar uma ordem de compra ou de venda intercompanhia, a ordem de compra ou venda correspondente na empresa correspondente também refletirá essa alteração.

## <a name="adding-new-lines"></a>Adição de novas linhas

Você pode adicionar novas linhas a uma ordem de venda e de compra intercompanhia se a ordem de venda original fizer parte da cadeia de ordens intercompanhia. Você também poderá adicionar novas linhas se a ordem de venda original não for uma entrega direta. Se a ordem de venda original for uma entrega direta, você poderá adicionar novas linhas à ordem de compra e de venda intercompanhia somente se o campo **Permitir criação indireta** estiver selecionado na Guia Rápida **Configurações intercompanhia** da ordem de venda original.

## <a name="changing-prices-and-discounts"></a>Alteração de preços e descontos

Você pode alterar os preços e os descontos se as caixas de seleção **Permitir edição de preços** e **Permitir edição de descontos** estiverem marcadas na página **Intercompanhia**.

Se alterar o preço unitário de uma das linhas existentes na linha da ordem de venda intercompanhia, o preço unitário na ordem de compra intercompanhia também será alterado.

Se você alterar os campos de desconto na linha da ordem de venda intercompanhia, os campos de desconto relevantes na ordem de compra intercompanhia serão atualizados.

## <a name="changing-and-adding-new-charges"></a>Alteração e adição de novos encargos

Você pode alterar os encargos se as caixas de seleção **Permitir edição de preços** e **Permitir edição de descontos** estiverem marcadas na página **Intercompanhia**.

Se você adicionar um novo encargo ao cabeçalho da ordem de venda intercompanhia e um novo encargo à linha de venda intercompanhia, os encargos serão copiados para a ordem de compra intercompanhia. Portanto, a ordem de venda intercompanhia e a ordem de compra intercompanhia têm o mesmo valor total. Os encargos nunca são copiados para a ordem de venda original.

## <a name="copying-a-fee"></a>Cópia de um valor

Para copiar um valor para a ordem de venda original, crie-a como uma nova linha de venda com um item do tipo **Serviço**.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Alteração de quantidades e exclusão de linhas de ordem de compra e de venda intercompanhia

Você só poderá alterar a quantidade ou excluir uma linha de ordem de venda ou de compra intercompanhia se a linha tiver sido criada diretamente no formulário **Ordem de venda** ou **Ordem de compra**. Essa alteração transforma as linhas de ordem ou de ordem de venda ou de compra intercompanhia em origem.

## <a name="origins-of-orders-and-order-lines"></a>Origens de ordens e linhas de ordem

As ordens intercompanhia e linhas de ordem podem ter duas origens:

- **Derivada** – a ordem foi criada automaticamente de uma cadeia de ordem intercompanhia.
- **Origem** – a ordem foi criada manualmente por um usuário.

A origem é indicada no cabeçalho da ordem das ordens de compra e ordens de venda intercompanhia no campo **Origem**. Esse campo está localizado na Guia Rápida **Configurações intercompanhia** da ordem de venda e na Guia Rápida **Configuração** da ordem de compra.

As origens **Derivada** e **Origem** só se aplicam a ordens intercompanhia. O campo **Origem** fica em branco para todas as outras ordens de venda, ordens de compra e linhas de ordem. Esse campo também fica em branco na ordem de venda original.

## <a name="example-derived-origin"></a>Exemplo: origem derivada

Você cria uma ordem de venda original para um cliente externo. Essa ordem de venda contém uma linha de ordem. Essa ordem de venda original cria uma ordem de compra intercompanhia que contém uma linha de ordem, que cria uma ordem de venda intercompanhia contendo uma linha de ordem. O cabeçalho e a linha de ordem da ordem de compra intercompanhia são criados automaticamente da ordem de venda original.

O valor do campo **Origem** na Guia Rápida **Configuração** da ordem de compra intercompanhia e na Guia Rápida **Configurações intercompanhia** dos cabeçalhos da ordem de venda intercompanhia é **Derivada**. O valor do campo **Origem** na guia **Detalhes da linha** da ordem de compra e das linhas da ordem de venda também é **Derivada**.

Se uma linha da ordem tiver uma origem **Derivada**, você não poderá excluir a linha da ordem diretamente. Você só poderá excluir a linha da ordem da origem que criou a linha da ordem. Além disso, você só poderá alterar a quantidade encomendada da origem que criou a linha de ordem.

Se uma ordem de venda original e uma linha da ordem de venda original fizerem parte da cadeia de ordem intercompanhia, você poderá alterar as quantidades encomendadas da ordem de venda original e poderá excluir linhas de ordem da ordem de venda original.

## <a name="example-source-origin"></a>Exemplo: origem da fonte

Você cria uma ordem de compra para um fornecedor intercompanhia. A ordem de compra intercompanhia e a linha de ordem terão uma origem **Origem**. Portanto, essa ordem de compra intercompanhia é a controladora e a ordem de venda intercompanhia criada automaticamente na empresa fornecedora tem uma origem **Derivada**.

Além disso, as quantidades encomendadas de uma linha da ordem criada na ordem de compra intercompanhia não podem ser alteradas na ordem de venda intercompanhia. A linha da ordem pode ser excluída apenas da ordem de compra intercompanhia. Se uma nova linha for adicionada à ordem de venda intercompanhia, a linha da ordem de venda intercompanhia terá uma origem **Origem**.

Quando uma ordem de venda original fizer parte da cadeia de ordem intercompanhia, você sempre poderá controlar as ordens e linhas de ordens intercompanhia a partir da ordem de venda original.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
