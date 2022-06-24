---
title: Configurar fornecedores, clientes e itens para o comércio intercompanhia
description: Este artigo explica como configurar fornecedores, clientes e itens para o comércio intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4c928435a4e66832b09dbc805664934cfb1236be
ms.sourcegitcommit: b666289f5113d0a3fa2220fe337d5aacf07cbd92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2022
ms.locfileid: "8945745"
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
1. Quando terminar de configurar os parâmetros intercompanhia, feche a página **Intercompanhia** para retornar aos detalhes do cliente selecionado.
1. Expanda a guia rápida **Detalhes diversos** e defina **Criar ordens intercompanhia** como *Sim*. Se você também desejar que os pedidos sejam entregues diretamente aos clientes, defina **Entrega direta** como *Sim*.

    > [!NOTE]
    > Se houver alguns itens que a sua organização armazene em estoque e entregue aos clientes, talvez você não queira criar ordens intercompanhia de forma automática, mesmo se tiver o item em estoque. Para desabilitar a geração automática de ordens para itens que possam estar incluídos no estoque, defina **Criar ordens intercompanhia** a *Não*.

1. Se desejar permitir a criação indireta de linhas adicionais em uma ordem de venda, defina **Criar linhas de ordem indireta** como *Sim*. Um usuário pode então adicionar linhas à ordem de venda original desde a ordem de venda intercompanhia.

> [!WARNING]
> Se permitir a criação indireta de linhas da ordem, você estará permitindo todas as adições à ordem de venda original da ordem de venda intercompanhia. Cada adição é processada para o cliente e adicionada à ordem e à fatura. Além disso, cada documento envolvido na venda é impresso e lançado automaticamente. Os usuários não são alertados sobre a adição.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
