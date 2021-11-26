---
title: Configurar comércio intercompanhia
description: Este tópico explica como configurar o comércio intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7288cc8f336b6b1f5174fe2bef38017e0c96e560
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777707"
---
# <a name="set-up-intercompany-trade"></a>Configurar comércio intercompanhia

[!include [banner](../../includes/banner.md)]

Para que o Microsoft Dynamics 365 Supply Chain Management execute comércio intercompanhia, é necessário configurar clientes e fornecedores para executar comércio intercompanhia. Você também deve configurar Contas a pagar, Contas a receber, Compras e fornecimento e Vendas e marketing.

## <a name="before-you-set-up-intercompany-trade"></a>Antes de configurar o comércio intercompanhia

Antes de configurar o comércio intercompanhia, você deverá decidir quais clientes e fornecedores são intercompanhia. Para cada entidade legal no Microsoft Dynamics 365 Supply Chain Management, você deve decidir qual política de comércio deve ser aplicada à relação comercial intercompanhia com o cliente ou fornecedor intercompanhia específico.

Particularmente, recomendamos que você e sua organização e se familiarizem com os parâmetros de intercompanhia.

- Discuta as implicações de configuração com os gerentes responsáveis pelo comércio intercompanhia em cada entidade legal.
- Configure os valores apropriados para cada entidade legal.

## <a name="set-up-trading-relations"></a>Configurar relações comerciais

Para configurar o comércio intercompanhia para clientes e fornecedores, siga estas etapas.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione uma conta de cliente.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Especifique parâmetros de configuração da conta do cliente. Esses parâmetros incluem a entidade legal que contêm o fornecedor e a conta de fornecedor correspondentes. Os parâmetros também incluem as políticas de ordem de compra, as políticas de ordem de venda, o mapeamento de valor e as diretivas para contratos de venda e de compra. Você também pode especificar se usar os valores dos dados básicos da conta do cliente ou da conta do fornecedor em outra entidade legal.
1. Repita as etapas 1 a 4 para os outros clientes intercompanhia na entidade legal.
1. Acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores**.
1. Selecione uma conta de fornecedor.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Especifique parâmetros de configuração da conta do fornecedor. Esses parâmetros incluem a entidade legal que contém o cliente e a conta de cliente correspondentes. Os parâmetros também incluem as políticas de ordem de venda, as políticas de ordem de compra, o mapeamento de valor e as políticas para contratos de venda e de compra. Você também pode especificar se usar os valores dos dados básicos da conta do fornecedor ou da conta do cliente em outra entidade legal.
1. Repita as etapas 6 a 9 para os fornecedores intercompanhia restantes na entidade legal.

## <a name="set-up-products"></a>Configurar produtos

Para configurar o comércio intercompanhia para clientes e fornecedores, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Todos os produtos e produtos mestres**.
1. Defina os produtos liberados para a entidade legal na qual você deseja realizar comércio intercompanhia.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
