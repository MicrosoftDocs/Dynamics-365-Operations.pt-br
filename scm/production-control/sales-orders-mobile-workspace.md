---
title: "O espaço de trabalho móvel de ordens de venda do Microsoft Dynamics 365 para o descritivo de operações"
description: "Com as ordens de venda o espaço de trabalho, celular poderá ficar atualizado nas ordens de venda em qualquer lugar e a qualquer momento."
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

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>O espaço de trabalho móvel de ordens de venda do Microsoft Dynamics 365 para o descritivo de operações

Com as ordens de venda o espaço de trabalho, celular poderá ficar atualizado nas ordens de venda em qualquer lugar e a qualquer momento. 

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                         | descrição                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Leia sobre o Microsoft Dynamics 365 para o preparo de celular de operações | [Dynamics 365 para a plataforma móvel] operações (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Verifique se está usando um ambiente com Microsoft Dynamics 365 para a versão 1611 de operações e o Microsoft Dynamics para atualização 3 de preparo operações (). em novembro de 2016 |
| 3215650 KB de Hotfix                                                    | Instalar o hotfix para habilitar espaços de trabalho fornecidos no Microsoft Dynamics 365 para as operações.                                                                       |
| Dispositivo móvel que tem o dynamics 365 para o descritivo instalado de operações | Baixe o dynamics 365 para o descritivo de operações do armazenamento móvel descritivo.                                                                                                      |

## <a name="overview"></a>Visão Geral
O espaço de trabalho móvel acessa o dynamics 365 para o aplicativo de operações e permite exibir informações detalhadas sobre cada status da ordem de venda, como, ordens, informações de contato do cliente, e informações de contato de compradores de ordem. O espaço de trabalho móvel fornece uma exibição instantânea de ordens de venda. Você pode exibir ordens de venda por cliente, ou exiba todas as ordens de venda, ou exiba informações sobre uma ordem de venda específica. O espaço de trabalho fornece duas exibições móvel para ajudar a analisar as ordens de venda detalhados.

### <a name="view-all-sales-orders"></a>Exiba todas as ordens de venda

Essa exibição lista todas as ordens de venda.

-   Use um dos filtros selecione as ordens de venda que deseja exibir.
    -   Procure pela ordem de venda
    -   Pesquisar por conta de cliente
    -   Pesquisar o nome de cliente
    -   Consultar por status
    -   Consultar por status da versão
    -   Pesquisar de data e hora criadas

<!-- -->

-   Após selecionar ordens de venda, você pode exibir os detalhes de ordens específicas. Especificamente, você pode exibir:
    -   Informações de nome e endereço do cliente
    -   Diferentes datas de ordem de venda, como a data de remessa solicitada e data de remessa confirmada
    -   Informações de contato de compradores de ordem
    -   Informações de contato do cliente
    -   Linhas da ordem
    -   Remessas para mostrar como e quando uma ordem de venda foi enviada

### <a name="view-orders-for-a-customer-"></a>Ordens de exibição para um cliente ** **

Essa exibição lista ordens de venda por cliente.

-   Use um dos filtros exibir ordens para um cliente.
    -   Pesquisar por nome
    -   Pesquisar por conta

<!-- -->

-   Após selecionar um cliente, você pode exibir:
    -   Nome e grupo de cliente
    -   Informações de contato do cliente
    -   Ordens de venda e detalhes do cliente sobre ordens de venda:
        -   Informações de nome e endereço do cliente
        -   Diferentes datas de ordem de venda
        -   Informações de contato de compradores de ordem
        -   Informações de contato do cliente
        -   Linhas da ordem
        -   Remessas para mostrar como e quando as ordens de venda foram enviados

## <a name="get-started"></a>Introdução
Rastrear essas etapas para introdução usando o espaço de trabalho móvel de ordens de venda no dispositivo móvel.

1.  No armazenamento móvel descritivo, baixar e instalar o Microsoft Dynamics 365 para o descritivo de operações.
2.  Inicie a descritivo no dispositivo.
3.  Insira a URL do 365.
4.  Insira a empresa para conectar-se. Por exemplo, insira USMF ** **.
5.  A primeira vez que que se conectar, será solicitado para o nome de usuário e a senha para o Microsoft Dynamics 365 para a conta de operações. Insira suas credenciais. Depois que se conectar, verá espaços de trabalho disponíveis para sua empresa.

Exibir espaços de trabalho do celular descritivo, primeiramente publicar espaços de trabalho o dynamics desejados para o 365 descritivo de operações.

1.  Dynamics 365 Inicial para as operações.
2.  Ir ** administração de sistema ** &gt; ** de instalação ** &gt; ** ** parâmetros do sistema.
3.  Selecione ** gerenciamento descritivo móvel **.
4.  Selecione o espaço de trabalho para publicar a plataforma móvel.
5.  ** Publicar selecione o espaço de trabalho. **
6.  Atualizar o dispositivo para consultar espaços de trabalho publicados.

## <a name="view-information-about-sales-orders-for-a-customer"></a>Exiba informações sobre ordens de venda para um cliente
1.  No dispositivo móvel, selecione ** ordens de venda ** o espaço de trabalho.
2.  ** Selecione ordens de exibição ** um cliente.
3.  Usar conta ** ** ** ou nome de cliente ** informações do cliente necessário.
4.  Selecione o cliente.
5.  ** Selecione informações de contato ou ** ** ** ordens de venda.
6.  ** Se ordens de venda ** for selecionado, uma lista de ordens de venda para o cliente será exibida.
7.  Selecione ** ** ordem de venda.
8.  Aqui você pode exibir informações sobre linhas de ordem de venda, remessas, informações de contato do cliente, e informações de contato de compradores de ordem.




