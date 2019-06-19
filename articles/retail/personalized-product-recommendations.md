---
title: Recomendações de produtos personalizados
description: Este tópico contém informações sobre recomendações de produtos do Dynamics 365 for Retail que podem ser exibidas no dispositivo de ponto de venda (PDV).
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c73bc10332329e81986a259969f8fe34b57f4ee6
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606984"
---
# <a name="personalized-product-recommendations"></a>Recomendações personalizadas de produtos

[!include [banner](includes/banner.md)]

> [!NOTE]
> Estamos removendo a versão atual do serviço de recomendação de produto, pois estamos remodelando esse recurso em um algoritmo melhor com recursos mais novos orientados ao varejo. Para obter mais informações consulte [Recursos removidos ou substituídos](../dev-itpro/migration-upgrade/deprecated-features.md).

No Dynamics 365 for Retail, as recomendações de produtos podem ser exibidas no dispositivo de ponto de venda (PDV). As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas. Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto. Ao exibir produtos de acordo com os interesses e hábitos de compras de um cliente, as recomendações de produto podem ajudar os varejistas nas vendas suplementar e cruzada, e pode aumentar a retenção de clientes. No Dynamics 365 for Retail, as recomendações do produto são habilitadas pelos serviços cognitivos e aprendizado de máquina do Microsoft Azure.

## <a name="scenarios"></a>Cenários

As recomendações de produto são habilitadas para os seguintes cenários de PDV. Estão disponíveis no Cloud POS ou Modern POS (MPOS).

1. Na página **Detalhes de produto**:

    - Se um associado da loja visita uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o mecanismo de recomendação sugere itens adicionais que provavelmente podem ser comprados juntos.
    - Se o associado da loja adicionar um cliente à transação e depois visitar uma página de **Detalhes de produto**, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transação do cliente.

    [![Recomendações na página Detalhes do produto](./media/proddetails.png)](./media/proddetails.png)

2. Na página **Transação**:

    - O mecanismo de recomendação sugere itens com base na lista inteira de itens na cesta.
    - Se o associado da loja adicionar um cliente à transação, o mecanismo de recomendação fornecerá recomendações pessoais usando o histórico de transação do cliente e a lista de itens na cesta.

    > [!NOTE]
    > Para exibir recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 for Retail. O controle das **Recomendações** deve ser colocado na página de **Transação**.

    [![Recomendações na página Transação](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3. Na página **Detalhes do cliente**, o mecanismo de recomendação sugere itens com base na ID de usuário e itens na lista de desejos do cliente.

    [![Recomendações na página Detalhes do cliente](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a>Configurar o Dynamics 365 for Retail para permitir recomendações PDV

Para configurar recomendações de produto, você precisa fazer o seguinte.

1. Verifique se você escolheu correto a **Entidade legal** correta.
2. Navegue até **Repositório de entidades**, selecione **Vendas de varejo** e clique em **Atualizar**. Isso usará os dados de demonstração (ou seus dados) do banco de dados operacional e irá movê-los para o repositório de entidades.
3. Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.
4. Vá para **Parâmetros de varejo**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.
5. Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**. Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.

## <a name="how-does-it-work"></a>Como funciona?

Quando você atualiza a entidade **Loja de entidade**, as ações a seguir ocorrem.

- Os dados no formato exigido pelos serviços cognitivos são extraídos do banco de dados operacional do Dynamics 365 for Retail e enviados para a loja de entidade.
- Os dados são usados por Azure Data Factory (ADF) para limpar os dados usando scripts em conjunto como parte das atividades do ADF. Os dados limpos são armazenados no armazenamento blob.
- Os dados do armazenamento de blob são usados pelo API dos serviços cognitivos para treinar um modelo de recomendação.

Quando você ativa **Habilitar recomendações** e executa os trabalhos de configuração, as ações a seguir ocorrem.

- As credenciais de modelo e ID são coletados da API e armazenadas no banco de dados operacional do Dynamics 365 for Retail, no web.config para AOS, bem como no servidor de varejo.
- As credenciais de modelo e ID tornam-se disponíveis ao CRT para que as chamadas de recomendações de produto do Cloud POS e MPOS no modo online podem ser liquidadas.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Solucionar problemas em que as Recomendações de produto já estejam habilitadas

- Navegue até **Parâmetros de Varejo** \> **Aprendizado de máquina** \> **Desabilitar recomendações de produtos** e execute **Trabalho de configuração global \[1110\]**. Se não conseguir localizar a guia **Aprendizado de máquina**, entre em contato com o suporte do Dynamics.
- Se você adicionou o **Controle de recomendações** à sua tela de transação usando o **Designer do layout da tela**, remova-o também.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um controle de recomendações à página de transação em um dispositivo do PDV](add-recommendations-control-pos-screen.md)
