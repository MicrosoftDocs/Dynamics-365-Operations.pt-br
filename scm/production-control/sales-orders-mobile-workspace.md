---
title: "Espaço de trabalho móvel de ordens de venda para o aplicativo do Microsoft Dynamics 365 for Operations"
description: "Com o espaço de trabalho móvel de ordens de vendas, você pode se manter atualizado em suas ordens de vendas em qualquer lugar e a qualquer momento."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espaço de trabalho móvel de ordens de venda para o aplicativo do Microsoft Dynamics 365 for Operations

Com o espaço de trabalho móvel de ordens de vendas, você pode se manter atualizado em suas ordens de vendas em qualquer lugar e a qualquer momento. 

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                         | descrição                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Leia sobre a plataforma móvel do Microsoft Dynamics 365 for Operations | [Plataforma móvel do Microsoft Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Verifique se você está usando um ambiente com a versão 1611 do Microsoft Dynamics 365 for Operations e a atualização 3 da plataforma do Microsoft Dynamics for Operations (novembro de 2016). |
| Hotfix KB 3215650                                                    | Instale o hotfix para habilitar os espaços de trabalho que são fornecidos no Microsoft Dynamics 365 for Operations.                                                                       |
| Dispositivo móvel com o Dynamics 365 for Operations instalado | Baixe o aplicativo do Dynamics 365 for Operations na sua loja de aplicativos móveis.                                                                                                      |

## <a name="overview"></a>Visão Geral
Esta área de trabalho móvel acessa o aplicativo do Dynamics 365 for Operations e permite exibir informações detalhadas sobre cada ordem de cliente, como status do pedido, informações de contato do cliente e informações de contato do comprador de pedidos. O espaço de trabalho móvel fornece uma visualização instantânea das ordens de venda. Você pode exibir pedidos de vendas por cliente, exibir todas as ordens do cliente ou exibir informações sobre uma ordem de cliente específica. O espaço de trabalho móvel oferece duas visualizações para ajudá-lo a analisar as ordens de venda em profundidade.

### <a name="view-all-sales-orders"></a>Exibir todas as ordens de venda

Essa exibição lista todas as ordens do cliente.

-   Use um dos seguintes filtros para selecionar as ordens de vendas que deseja exibir.
    -   Pesquisar por ordem de cliente
    -   Pesquisa por conta de cliente
    -   Pesquisa por nome de cliente
    -   Pesquisar por status
    -   Pesquisar por status de lançamento
    -   Procurar por data e hora de criação

<!-- -->

-   Depois de selecionar as ordens do cliente, você pode visualizar os detalhes de ordens específicas. Especificamente, você pode visualizar:
    -   Informações de nome e endereço do cliente
    -   Diferentes datas de ordem de venda, como data de envio solicitada e data de envio confirmada
    -   Informações para contato do comprador de pedidos
    -   Informações de contato do cliente
    -   Linhas da ordem
    -   Envios que mostram como e quando uma ordem do cliente foi enviada

### <a name="view-orders-for-a-customer-"></a>Ver encomendas de um cliente

Essa exibição lista ordens de vendas por cliente.

-   Essa exibição lista ordens de vendas por cliente.
    -   Pesquisar por nome
    -   Pesquisar por conta

<!-- -->

-   Depois de selecionar um cliente, é possível exibir:
    -   Nome e grupo do cliente
    -   Informações de contato do cliente
    -   Ordens de vendas do cliente e detalhes sobre as ordens de venda:
        -   Informações de nome e endereço do cliente
        -   Diferentes datas de pedidos de vendas
        -   Informações para contato do comprador de pedidos
        -   Informações de contato do cliente
        -   Linhas da ordem
        -   Envios que mostram como e quando uma ordem de venda foi enviada

## <a name="get-started"></a>Introdução
Siga estas etapas para começar a usar o espaço de trabalho móvel de ordens de vendas em seu dispositivo móvel.

1.  Na sua loja de aplicativos móveis, baixe e instale o aplicativo do Microsoft Dynamics 365 for Operations.
2.  Inicie o aplicativo no seu dispositivo.
3.  Insira sua URL do Dynamics 365.
4.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
5.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Microsoft Dynamics 365 for Operations. Insira suas credenciais. Após se conectar, você verá os espaços de trabalho da sua empresa.

Para exibir os espaços de trabalho no seu aplicativo móvel, primeiro você deve publicar os espaços de trabalho desejados para o aplicativo do Dynamics 365 for Operations.

1.  Inicie o Dynamics 365 for Operations.
2.  Vá para **Administração do sistema** &gt; **Configuração** &gt; **Parâmetros do sistema**.
3.  Selecione o **Gerenciar aplicativo móvel**.
4.  Selecione o espaço de trabalho para publicar a plataforma móvel.
5.  Selecione **Publicar espaço de trabalho**.
6.  Atualize seu dispositivo para ver os espaços de trabalho publicados.

## <a name="view-information-about-sales-orders-for-a-customer"></a>Exibir informações sobre ordens de venda para um cliente específico
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Ordens de vendas**.
2.  Selecione **Exibir ordens para um cliente**.
3.  Use as informações **Conta **ou **Nome do cliente **para localizar o cliente desejado.
4.  Selecione o cliente.
5.  Selecione **Informações de contato** ou **Ordens de venda**.
6.  Se **Ordens de venda** for selecionado, será exibido uma lista de ordens de vendas para o cliente.
7.  Selecione **Ordem de venda**.
8.  Aqui você pode exibir informações sobre linhas de ordens de vendas, remessas, informações de contato do cliente e informações de tomador da ordem.




