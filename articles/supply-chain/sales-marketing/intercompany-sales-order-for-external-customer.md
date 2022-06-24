---
title: Criar e faturar uma ordem de venda intercompanhia para um cliente externo
description: Este artigo explica como criar e faturar uma ordem de venda intercompanhia para um cliente externo
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
ms.openlocfilehash: cd42551730ab0123813a3b5a0b5a4b1c334e9d30
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852147"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Criar e faturar uma ordem de venda intercompanhia para um cliente externo

[!include [banner](../../includes/banner.md)]

Você pode usar o comércio intercompanhia para registrar a venda de um produto de uma entidade legal para outra entidade legal na mesma organização.

Quando a ordem de venda original for criada, será possível criar automaticamente uma ordem de compra intercompanhia para o fornecedor intercompanhia. Isso cria automaticamente uma ordem de venda intercompanhia na entidade legal de fornecedor intercompanhia.

A ilustração a seguir mostra o fluxo das transações quando você cria uma ordem de venda para um cliente externo, mas o produto deve ser solicitado por uma entidade legal diferente em sua organização antes de entregar o produto ao cliente. Nesse caso, uma ordem de compra intercompanhia é criada para a conta do fornecedor que representa a outra entidade legal. Por sua vez, uma ordem de venda intercompanhia é criada em outra entidade legal para a conta do cliente que representa a entidade legal. Quando uma ordem de compra intercompanhia é faturada, a fatura da ordem de venda original é automaticamente lançada, caso seja uma entrega direta.

![Processo de vendas externas intercompanhia](media/intercompanyexternalsalesprocess.png)

Se estiver usando a entrega direta e selecionar **Guia de remessa** no campo **Quantidade** do formulário **Lançando fatura**, a fatura da ordem de compra do fornecedor de intercompanhia será baseada no recibo do produto da intercompanhia que foi lançado anteriormente.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, verifique se os pré-requisitos a seguir são atendidos para lançar e imprimir automaticamente as faturas intercompanhia.

1. Acesse **Vendas e marketing \> Clientes \> Todos os clientes**.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Acesse **Aquisição e fornecimento \> Fornecedores \> Todos os fornecedores**.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Na página **Intercompanhia** para o fornecedor ou o cliente, na área **Políticas de ordem de compra** , no grupo de campos **Ordem de compra intercompanhia (entrega direta)** , marque a caixa de seleção **Lançar fatura automaticamente**.
1. Na área **Políticas de ordem de compra**, no grupo de campos **Ordem de venda original (entrega direta)**, marque a caixa de seleção **Lançar fatura automaticamente**. Marque essa caixa de seleção se quiser que a fatura para a ordem de venda original seja impressa automaticamente quando você lançar a fatura de fornecedor intercompanhia.

> [!NOTE]
> As configurações de impressão para a fatura são determinadas pela configuração para o módulo, documento ou transação na página **Configuração de gerenciamento de impressão**.

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Criar uma ordem de venda original para um cliente externo

Execute estas etapas na entidade legal A. Este procedimento corresponde à caixa com o rótulo 1 na ilustração.

1. Acesse **Contas a receber \> Ordens de venda \> Todas as ordens de venda**.
1. Na página de listagem **Todas as ordens de venda**, crie a ordem de venda original. Os valores de campo são copiadas da conta do cliente para a ordem de venda.
1. Na página **Ordem de venda**, selecione **Exibição do cabeçalho** no Painel de Ações.
1. Na Guia Rápida **Configurações intercompanhia** , marque a caixa de seleção **Criação automática de ordens intercompanhia**.
1. Se quiser que o fornecedor intercompanhia entregue o item diretamente ao cliente externo, marque a caixa de seleção **Entrega direta**.
1. Quando terminar de inserir a ordem de venda, feche a página **Ordem de venda**.

A ordem de compra intercompanhia é automaticamente criada para todos os itens atribuídos a um fornecedor intercompanhia e, em seguida, cria uma ordem de venda intercompanhia. Uma mensagem informativa avisa que uma ordem de compra intercompanhia e uma ordem de venda intercompanhia foram criadas e contêm links para estas ordens. A mensagem também contém links para as ordens. Se um item não for encontrado, será exibido um aviso vermelho que significa que o processo de criação da ordem não foi concluído.

> [!NOTE]
> Se você estiver criando várias ordens em diferentes entidades legais e, em uma delas, os itens não forem encontrados, o programa interromperá a criação de todas as ordens, mesmo para as entidades legais que poderiam executar as ordens.

## <a name="invoice-an-intercompany-sales-order"></a>Faturar uma ordem de venda intercompanhia

Quando a ordem de venda de uma intercompanhia é faturada, a ordem de compra intercompanhia correspondente é faturada automaticamente. Em seguida, se a ordem de venda original for uma ordem de entrega direta, a ordem de venda original é faturado automaticamente.

Execute estas etapas na entidade legal B. Este procedimento corresponde à caixa com o rótulo 2 na ilustração.

1. Acesse **Contas a receber \> Ordens de venda \> Todas as ordens de venda**.
1. Na página de listagem **Todas as ordens de venda**, selecione a ordem de venda intercompanhia.
1. No Painel de Ações, selecione a guia **Fatura** e depois selecione **Fatura**.
1. Marque a caixa de seleção **Lançamento**.
1. Selecione a ordem de venda e selecione **OK**.

A fatura de cliente da ordem de venda intercompanhia é lançada automaticamente na entidade legal B. A fatura de fornecedor intercompanhia é criada automaticamente e lançada na entidade legal A. Se a ordem de venda original for configurada em uma entrega direta, a fatura de cliente será criada para a ordem de venda original na entidade legal A.

> [!NOTE]
> Anteriormente, para cenários de vendas intercompanhia, se o fluxo de trabalho de fatura de fornecedor foi configurado na empresa de compra intercompanhia, a ordem de venda intercompanhia não pôde ser faturada com êxito. Portanto, o fluxo de trabalho de fatura de fornecedor precisava ser desativado para a empresa de compra intercompanhia. 
> 
> Essa limitação foi corrigida por um recurso recente na versão 10.0.25. As ordens de venda intercompanhia agora podem ser faturadas quando o fluxo de trabalho de fatura de fornecedor é configurado na empresa de compra intercompanhia.
> 
> Para habilitar este recuso, seguir estas etapas.
>
> 1. Selecionar a entidade legal intercompanhia de vendas.  
> 2. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
> 3. Selecionar o cliente para a empresa de compra intercompanhia.
> 4. Ir para **Geral \> Configuração \> Intercompanhia**.
> 5. Na guia **Políticas de ordem de compra**, selecionar o parâmetro **Fluxo de trabalho da fatura de fornecedor Bypass**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
