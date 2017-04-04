---
title: Personalized product recommendations overview
description: "Em dynamics 365 para operações, recomendações de produto podem ser exibidas no dispositivo (POS) do ponto de venda. As recomendações são itens que o cliente pode ser baseado interessado no histórico de compra, em itens da lista de objetivos pretendidos, e em itens que compraram online outros clientes e em lojas físicas. Para fornecedores com grandes catálogos, recomendações ajuda o cliente com descoberta de produto. Passando produtos destinados os juros de um cliente e a hábitos de compra, recomendações de produto podem ajudar fornecedores com acima- e vendas entre venda, e pode aprimorar a retenção de clientes. Em dynamics 365 para operações, recomendações de produto são cognitivos serviços powered by e do computador do Microsoft Azure saber."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Personalized product recommendations overview

Em dynamics 365 para operações, recomendações de produto podem ser exibidas no dispositivo (POS) do ponto de venda. As recomendações são itens que o cliente pode ser baseado interessado no histórico de compra, em itens da lista de objetivos pretendidos, e em itens que compraram online outros clientes e em lojas físicas. Para fornecedores com grandes catálogos, recomendações ajuda o cliente com descoberta de produto. Passando produtos destinados os juros de um cliente e a hábitos de compra, recomendações de produto podem ajudar fornecedores com acima- e vendas entre venda, e pode aprimorar a retenção de clientes. Em dynamics 365 para operações, recomendações de produto são cognitivos serviços powered by e do computador do Microsoft Azure saber.

<a name="scenarios"></a>Cenários
---------

As recomendações de produto são habilitadas para os seguintes cenários POS. Estão disponíveis no retail do nuvem ou no retail moderno (MPOS).

1.  ** Detalhes de produto ** página em:

-   Se um associado de loja a visita ** detalhes ** página de produto ao examinar transações anteriores nos canais diferentes, o mecanismo de recomendação sugere itens extras que são comprados pode ser em conjunto.
-   Se o associar de armazenamento adicionar um cliente à transação e a visita ** detalhes ** página de produto, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transações de cliente.

[proddetails![(]. /media/proddetails.png)](. /media/proddetails.png)

2.  ** ** Da transação:

-   O mecanismo de recomendação sugere itens com base em lista inteira de itens na cesta.
-   Se o associar de armazenamento adicionar um cliente à transação, o mecanismo de recomendação fornece recomendações pessoais com o histórico de transações de cliente e a lista de itens na cesta.

** Nota ** exibir recomendações ** ** transação na página, fornecedor precisa atualizar o layout de tela em dynamics 365 para as operações. ** Recomendações ** controle deve ser soltado ** ** transação sobre a página. [![(transactionscreenmultipleproductslargemessengersbag-5]. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  ** Detalhes de clientes ** página em:
    -   O mecanismo de recomendação sugere itens com base em ID de usuário e os itens na lista de objetivos pretendidos de cliente.

[customerdetailsrecommendations![(]. /media/customerdetailsrecommendations.png)](. /media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Configure o dynamics 365 para as operações habilitar recomendações POS
Recomendações de configuração de produto, você precisar realizar o seguinte.

1.  Verifique se você escolheu correto ** entidade legal **.
2.  Navegar ** o repositório entidade **, selecione ** vendas de varejo **, clique em atualizar. ** **** ** Isso usará os dados de demonstração (ou seus dados) do base de dados mover-os-&z operacional e o armazenamento de entidade.
3.  Opcional: Para exibir recomendações na tela da transação, vá ** layout da tela, ** escolhem o layout da tela, iniciam ** designer do layout da tela, ** ** ** e em soltam ** controle das recomendações ** onde necessário.
4.  Ir ** venda a varejo, selecione parâmetros ** ** Computador- sabendo **, selecione Sim ** ** abaixo ** habilitar recomendações POS **.
5.  Para consultar recomendações no POS, trabalhos globais a configuração de execução ** ** 1110. Para refletir modificações feitas no designer do layout da tela do retail, trabalhos de configuração de canal de execução ** ** 1070.

## <a name="how-does-it-work"></a>[] (como trabalhar?
Quando você atualiza ** armazenamento entidade ** a entidade, as seguintes ações ocorrerão.

-   Os dados no formato exigido pelos serviços cognitivos são extraídos do 365 de dados operacional operações e enviados ao armazenamento de entidade.
-   Os dados são usados por fábrica de dados (ADF) de Azure para limpar os dados usando scripts da OS como parte das atividades de ADF. Os dados são armazenados eliminados em armazenamento do blob.
-   Os dados de do blob armazenamento são usados por cognitivo API de serviços para treinar um modelo da recomendação.

Quando você ativa ** habilitar recomendações ** e executa os trabalhos de configuração, as seguintes ações ocorrerão.

-   As credenciais e ID modelo são retirados API e armazenados em dynamics 365 de dados operacional operações, em web.config para o aos, e também no POS.
-   As credenciais e ID modelo são feitos para disponível CRT de forma que liga para recomendações de produto do nuvem POS e no modo MPOS online possam ser honrados.


<a name="see-also"></a>Consulte também
--------

[Adicionar um controle das recomendações para a página de transação em um dispositivo] POS (add-recommendations-control-pos-screen.md)


