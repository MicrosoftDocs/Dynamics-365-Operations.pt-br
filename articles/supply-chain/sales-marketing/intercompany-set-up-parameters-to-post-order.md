---
title: Configurar parâmetros para lançar uma ordem intercompanhia
description: Este tópico explica como configurar parâmetros para lançar uma ordem intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c728f2f491948ae1c8550396ba4d72f76f46fe85
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548100"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Configurar parâmetros para lançar uma ordem intercompanhia

[!include [banner](../../includes/banner.md)]

Quando a fatura do cliente de uma intercompanhia é lançada, é possível defini-la para lançamento automático na ordem de compra intercompanhia e na fatura original do cliente.

> [!NOTE]
> Antes desse procedimento, configure o gerenciamento de impressão da organização para apontar a impressora correta da fatura. Isso irá assegurar que a fatura da ordem de venda original seja impressa na impressora correta.

Você deve configurar os seguintes parâmetros:

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**. Selecione a ordem de venda com a qual deseja trabalhar.
1. Na ordem de venda, no Painel de Ações, selecione **Exibição de cabeçalho** e selecione a Guia Rápida **Configurações intercompanhia** e a abra.
1. Acesse o Painel de Ações, na guia **Ordem de venda**, e então selecione **Editar**.
1. Volte à Guia Rápida **Configurações intercompanhia** e selecione **Entrega direta** para habilitar a entrega direta em toda a cadeia intercompanhia (todas as ordens).
1. Selecione **Salvar** para salvar a ordem de venda com a nova configuração. Em seguida, selecione **Fechar** para fechar a ordem de venda.
1. Acesse **Aquisição e fornecimento \> Fornecedores \> Todos os fornecedores**. Na guia **Geral**, selecione **Intercompanhia**.
1. Na página **Intercompanhia**, selecione o link **Políticas de ordem de compra**. No grupo de campos **Ordem de compra intercompanhia (entrega direta)**, selecione **Lançar fatura automaticamente** e remova a marca de seleção do campo **Imprimir fatura automaticamente**.
1. No grupo de campos **Ordem de venda original (entrega direta)**, selecione o campo **Lançar fatura automaticamente** e o campo **Imprimir fatura automaticamente**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
