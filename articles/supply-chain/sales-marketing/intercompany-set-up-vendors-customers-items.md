---
title: Configurar fornecedores, clientes e itens para o comércio intercompanhia
description: Este tópico explica como configurar fornecedores, clientes e itens para o comércio intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 062b8fe956fef0f8172d26aac3df54b93e1941ef
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548094"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Configurar fornecedores, clientes e itens para o comércio intercompanhia

[!include [banner](../../includes/banner.md)]

Para preparar sua organização para o comércio intercompanhia, você deve definir os fornecedores e clientes com os quais você deseja fazer negócios internamente. Você deve então associe esses fornecedores e clientes com os itens que você deseja compras ou será vendendo.

1. Acesse **Aquisição e fornecimento \> Fornecedores \> Todos os fornecedores**.
1. Selecione o fornecedor para definir como um fornecedor intercompanhia.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Especifique parâmetros de configuração da conta do fornecedor. Esses parâmetros são as entidade legal e a conta do cliente, políticas da ordem de venda, políticas da ordem de compra, o mapeamento de valor, e contrato de compra e as políticas de contrato de venda. Você também pode especificar se usar os valores dos dados básicos da conta do fornecedor ou da conta do cliente em outra entidade legal.
1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Na página de listagem **Produtos liberados**, selecione os itens para atribuir ao fornecedor, de modo que os itens estejam disponíveis para o comércio intercompanhia. Para cada item, abra a página **Detalhes do produto liberado**. Na guia **Compra**, no campo **Fornecedor**, digite o número do fornecedor.
1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione o cliente para definir como um cliente intercompanhia.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Especifique parâmetros de configuração da conta do cliente. Esses parâmetros são a entidade legal e a conta do fornecedor, políticas da ordem de compra, políticas da ordem de venda, o mapeamento de valor, e contrato de venda e as políticas de contrato de compra. Você também pode especificar se usar os valores dos dados básicos da conta do cliente ou da conta do fornecedor em outra entidade legal.
1. Na página **Clientes**, na Guia Rápida **Fatura e entrega**, marque a caixa de seleção **Criar ordens intercompanhia**. Se desejar que as ordens sejam entregues diretamente aos clientes, marque a caixa de seleção **Entrega direta**.

    > [!NOTE]
    > Se houver alguns itens que a sua organização armazene em estoque e entregue aos clientes, talvez você não queira criar ordens intercompanhia de forma automática, mesmo se tiver o item em estoque. Para desabilitar a geração automática de ordens para itens que possam estar incluídos no estoque, não marque a caixa de seleção **Criar ordens intercompanhia**.

1. Se desejar permitir a criação indireta de linhas adicionais em uma ordem de venda, marque a caixa de seleção **Criar linhas de ordem indireta**. Um usuário pode então adicionar linhas à ordem de venda original desde a ordem de venda intercompanhia.

> [!WARNING]
> Se permitir a criação indireta de linhas da ordem, você estará permitindo todas as adições à ordem de venda original da ordem de venda intercompanhia. Cada adição é processada para o cliente e adicionada à ordem e à fatura. Além disso, cada documento envolvido na venda é impresso e lançado automaticamente. Os usuários não são alertados sobre a adição.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
