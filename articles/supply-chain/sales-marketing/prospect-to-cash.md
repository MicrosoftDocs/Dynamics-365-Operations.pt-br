---
title: Prospect to cash
description: "O tópico fornece uma visão geral da solução Prospect to cash entre o Dynamics 365 for Finance and Operations, Enterprise Edition e o Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: pt-br
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a>Prospect to cash  

[!include[banner](../includes/banner.md)]

A solução Prospect to cash solution usa a [Integração de dados](/common-data-service/entity-reference/dynamics-365-integration) para sincronizar dados entre as instâncias do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition e do Dynamics 365 for Sales por meio do Common Data Service (CDS). Os modelos do Prospect to cash disponíveis com o recurso Integração de dados permitem o fluxo de contas, contatos, produtos, cotações de vendas, ordens de venda e dados das faturas de vendas entre o Finance and Operations e o Sales. Apesar de os dados estarem fluindo entre o Finance and Operations e o Sales, você pode executar atividades de vendas e de marketing no Sales e tratar o atendimento da ordem com o gerenciamento de estoque no Finance and Operations. 

Esta solução oferece integração nas seguintes áreas: 

-   [Manter contas no Sales e sincronizá-las para o Finance and Operations.](accounts-template-mapping.md)
-   [Manter contatos no Sales e sincronizá-los para o Finance and Operations.](contacts-template-mapping.md)
-   [Manter produtos no Finance and Operations e sincronizá-los para o Sales.](products-template-mapping.md)
-   [Criar cotações de vendas no Sales e sincronizá-las para o Finance and Operations.](sales-quotation-template-mapping.md)
-   [Criar ordens de venda no Finance and Operations e sincronizá-las para o Sales.](sales-order-template-mapping.md)
-   [Criar faturas de venda no Finance and Operations e sincronizá-las com o Sales.](sales-invoice-template-mapping.md)

Esta solução oferece sincronização direta nas seguintes áreas:

-   [Manter contas no Sales e sincronizá-las diretamente do Sales para o Finance and Operations.](accounts-template-mapping-direct.md)
-   [Manter produtos no Finance and Operations e sincronizá-los diretamente para o Sales.](products-template-mapping-direct.md)
-   [Manter contatos no Sales e sincronizá-los diretamente para contatos ou clientes do Finance and Operations](contacts-template-mapping-direct.md)
-   [Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
-   [Criar ordens de venda no Finance and Operations e sincronizá-las diretamente para o Sales.](sales-order-template-mapping-direct.md)
-  [Sincronizar cabeçalhos e linhas de ordem de venda diretamente entre o Sales e o Finance and Operations](sales-order-template-mapping-between-sales-fin.md)
-   [Sincronizar ordens de venda diretamente entre o Sales e o Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
-   [Criar faturas de venda no Finance and Operations e sincronizá-las diretamente para o Sales.](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Requisitos do sistema para o Dynamics 365 for Finance and Operations, Enterprise Edition

Para usar a solução Prospect to cash, instale o seguinte:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017) com atualização da Plataforma 8 (App 7.2.11792.56024 com Plataforma 7.0.4565.16212)

- Hotfixes para o Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017).
        
    -  [KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - Este hotfix permite o suporte à sincronização da ordem de venda com o recurso de integração de dados do Sales para o Finance and Operations, junto com vários outros aperfeiçoamentos.

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Este hotfix permite sincronização da linha da ordem de venda com o recurso de Integração de dados do Finance and Operations com o Sales.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Este hotfix permite a sincronização da ordem de venda com o recurso de Integração de dados do Finance and Operations com o Sales.

**Nota**: Basta instalar o KB4045570 pois a instalação inclui as alterações dos outros KBs.
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>Requisitos do sistema do Dynamics 365 for Sales

Para usar a solução Prospect to cash, instale o seguinte:

- Dynamics 365 for Sales versão 1612 (8.2.1.207) (DB 8.2.1.207) online.
- Solução Prospect to cash para Dynamics 365 for Sales, versão 1.14.0.0 (v14) ou posterior.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Instale a solução Prospect to cash para Sales

- Baixe o [arquivo zip do pacote da solução Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) no CustomerSource.

- Verifique se o arquivo zip está desbloqueado, para não receber a mensagem de erro “Nenhum pacote de importação foi encontrado” ao instalar o pacote da solução. Para desbloquear o arquivo, faça o seguinte:

    -  Clique com o botão direito no arquivo zip.
    -  Selecione **Propriedades** e **Desbloquear**. 

- Descompacte e execute o arquivo PackageDeployer.exe.

- Instale a solução Prospect to cash em sua instância do Sales.

    - Selecione o tipo de implantação **Office 365**.
    - Selecione **Mostrar avançada**.
    - Para uma instalação rápida, selecione uma **Região**. Se você selecionar **Não sei**, o sistema pesquisará todas as regiões e demorará para instalar.
    - Informe **Nome do usuário** e **Senha** de um usuário administrador que tem os direitos de usuário para instalar.

