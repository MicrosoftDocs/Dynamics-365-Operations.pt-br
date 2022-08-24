---
title: Criar ordens do call center
description: Este artigo mostra um exemplo de procedimento em que um usuário do call center pesquisa um cliente, cria uma nova ordem, pesquisa por um produto e coleta os pagamentos do cliente no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228501"
---
# <a name="create-call-center-orders"></a>Criar ordens do call center

[!include [banner](../includes/banner.md)]

Este artigo mostra um exemplo de procedimento em que um usuário do call center pesquisa um cliente, cria uma nova ordem, pesquisa por um produto e coleta os pagamentos do cliente no Microsoft Dynamics 365 Commerce. O procedimento usa a empresa de dados de demonstração USRT e destina-se aos funcionários de ordens de venda. 

## <a name="prerequisites"></a>Pré-requisitos

O usuário que conclui o procedimento deve ser configurado como usuário de call center. Opcionalmente, o catálogo semestral da Fabrikam pode ser publicado com pelo menos um código-fonte.

### <a name="add-yourself-as-a-call-center-user"></a>Adicionar a si mesmo como um usuário do call center

Para adicionar a si mesmo como um usuário de call center, siga estas etapas.

1. No Commerce Headquarters, acesse **Retail e Commerce \> Canais \> Call centers \> Todos os call centers**.
1. No campo **Usuários**, selecione **Usuários do canal**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **ID do Usuário**, insira a sua ID de usuário.
1. No campo **Nome**, insira o seu nome de usuário. O nome de usuário pode ser igual à ID de usuário.
1. No Painel de ações, selecione **Salvar**.
1. Volte para **Retail e Commerce \> Canais \> Call centers \> Todos os call centers**.
1. Selecione a ID de canal de varejo do call center.
1. Confirme se a opção **Habilitar conclusão de ordem** está definida como **Sim**. Se a opção não estiver visível, você poderá ignorar esta etapa.

## <a name="complete-the-example-call-center-procedure"></a>Conclua o procedimento de exemplo do call center

Para concluir o procedimento de exemplo do call center, siga estas etapas.

1. Acesse **Retail e Commerce \> Clientes \> Customer service**.
1. Na guia **Pesquisa de cliente**, insira os critérios de pesquisa para pesquisar o cliente. Para este procedimento de exemplo, insira **Karen**.
1. Selecione **Pesquisar**. A caixa de diálogo **Pesquisa de cliente** é exibida e lista os resultados da pesquisa.
1. Selecione o registro de cliente para **Karen Berg** com número de conta de cliente **2001** e, depois, selecione **Selecionar**.
1. No Painel de Ações, selecione **Nova ordem de venda**.
1. À direita, selecione a guia **Cabeçalho**.
1. Na FastTab **Entrega**, no campo **Modo de entrega**, selecione **99 Padrão**.

    ![Selecione um modo de entrega.](../media/Select_Mode_of_Delivery.png)

1. À direita, selecione a guia **Linhas**.
1. Na seção **Linhas de ordem de venda**, na nova linha de vendas, no campo **Número do item**, insira o número de item a ser pesquisado. Para este procedimento de exemplo, digite **81327** e, depois, selecione o produto na lista suspensa para adicioná-lo à ordem de venda.
1. No campo **Quantidade**, insira a quantidade de vendas.
1. No campo **Código de origem**, selecione o código de origem para o catálogo. Se não houver código-fonte ativo, você poderá ignorar esta etapa.
1. No Painel de Ações, selecione **Concluir** para capturar o pagamento do cliente. Esta ação abre a caixa de diálogo **Resumo da ordem de venda**, que mostra o valor total vencido. A ação também dispara o cálculo de encargos, como remessa e manuseio, e os mostra na caixa de diálogo **Resumo da ordem de venda**.

    ![Botão Concluir.](../media/Complete_button.png)

1. Na caixa de diálogo **Resumo da ordem de venda**, na FastTab **Pagamentos**, selecione **Adicionar** para capturar os pagamentos.

    ![Caixa de diálogo Resumo da ordem de venda.](../media/order_summary.png)

1. Na caixa de diálogo **Inserir informações de pagamento do cliente**, no campo **Método de pagamento**, selecione o método de pagamento. Para este procedimento de exemplo, selecione **Pagamento à vista**.
1. No campo **Valor do pagamento**, insira o valor do pagamento. Neste exemplo, insira **120,00**, que é igual ao saldo da ordem que é mostrado na caixa de diálogo **Resumo da ordem de venda**. Ao inserir este valor, você conclui a ordem como totalmente paga.
1. Selecione **OK**.
1. Selecione **Enviar**.

## <a name="additional-resources"></a>Recursos adicionais

[Personalizar emails transacionais por modo de entrega](../customize-email-delivery-mode.md)

[Alterar modo de entrega no PDV](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
