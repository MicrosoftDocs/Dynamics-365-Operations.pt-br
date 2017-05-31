---
title: "Visão geral de recomendações de produto personalizado"
description: "No Microsoft Dynamics 365 for Operations, recomendações de produto podem ser exibidas no dispositivo de ponto de venda (PDV). As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas. Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto. Ao exibir produtos para determinado público de interesse e hábitos de compra, as recomendações de produto podem ajudar os varejistas com venda direta e cruzada, e pode aumentar a retenção de cliente. No Dynamics 365 for Operations, recomendações de produto são suportadas por serviços cognitivos e aprendizagem de máquina do Microsoft Azure."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: edacd4cc9f9db59617bc579cb106e8e1017b8957
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="personalized-product-recommendations-overview"></a>Visão geral de recomendações de produto personalizado

[!include[banner](includes/banner.md)]


No Microsoft Dynamics 365 for Operations, recomendações de produto podem ser exibidas no dispositivo de ponto de venda (PDV). As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas. Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto. Ao exibir produtos para determinado público de interesse e hábitos de compra, as recomendações de produto podem ajudar os varejistas com venda direta e cruzada, e pode aumentar a retenção de cliente. No Dynamics 365 for Operations, recomendações de produto são suportadas por serviços cognitivos e aprendizagem de máquina do Microsoft Azure.

<a name="scenarios"></a>Cenários
---------

As recomendações de produto são habilitadas para os seguintes cenários de PDV. Estão disponíveis no Cloud POS ou Modern POS (MPOS).

1.  Na página **Detalhes de produto**:

-   Se um associado da loja visita uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o mecanismo de recomendação sugere itens adicionais que provavelmente podem ser comprados juntos.
-   Se o associado da loja adicionar um cliente à transação e depois visitar uma página de **Detalhes de produto**, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transação do cliente.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  Na página **Transação**:

-   O mecanismo de recomendação sugere itens com base na lista inteira de itens na cesta.
-   Se o associado da loja adicionar um cliente à transação, o mecanismo de recomendação fornece recomendações pessoais usando o histórico de transação do cliente e a lista de itens na cesta.

**Nota**  Para exibir as recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Microsoft Dynamics 365 for Operations. O controle das **Recomendações** deve ser colocado na página de **Transação**. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  Na página **Detalhes de cliente**:
    -   O mecanismo de recomendação sugere itens com base na ID de usuário e itens na lista de desejo do cliente.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Configurar o Microsoft Dynamics 365 for Operations para habilitar recomendações de PDV
Para configurar recomendações de produto, você precisa fazer o seguinte.

1.  Verifique se você escolheu correto a **Entidade legal** correta.
2.  Navegue até a **Loja da entidade**, selecione **Vendas de varejo** e depois clique em **Atualizar**.** **Ela usará os dados demonstrativos (ou seus dados) de seu banco de dados operacional e os moverá para a loja de entidade.
3.  Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, abra o **Designer do layout da tela**,** ** e depois deixe o **controle de recomendações** onde necessário.
4.  Vá para **Parâmetros de varejista**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.
5.  Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**. Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.

## <a name="how-does-it-work"></a>[]()Como funciona?
Quando você atualiza a entidade **Loja de entidade**, as ações a seguir ocorrem.

-   Os dados no formato exigido pelos serviços cognitivos são extraídos do banco de dados operacional do Microsoft Dynamics 365 for Operations e enviados para a loja de entidade.
-   Os dados são usados por Azure Data Factory (ADF) para limpar os dados usando scripts em conjunto como parte das atividades do ADF. Os dados limpos são armazenados no armazenamento blob.
-   Os dados do armazenamento de blob são usados pelo API dos serviços cognitivos para treinar um modelo de recomendação.

Quando você ativa **Habilitar recomendações** e executa os trabalhos de configuração, as ações a seguir ocorrem.

-   As credenciais de modelo e ID são coletados da API e armazenadas no banco de dados operacional do Microsoft Dynamics 365 for Operations, no web.config para AOS e também no servidor de varejo.
-   As credenciais de modelo e ID tornam-se disponíveis ao CRT para que as chamadas de recomendações de produto do Cloud POS e MPOS no modo online podem ser liquidadas.


<a name="see-also"></a>Consulte também
--------

[Adicionar um controle de recomendações à página de transação em um dispositivo do PDV](add-recommendations-control-pos-screen.md)




