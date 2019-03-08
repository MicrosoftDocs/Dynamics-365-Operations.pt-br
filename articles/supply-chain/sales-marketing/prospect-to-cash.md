---
title: Prospect to cash
description: Este tópico fornece uma visão geral da solução Prospect to cash entre o Microsoft Dynamics 365 for Finance and Operations e o Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b46ece384a28f8e78989253fcf467fbf3feaf1b7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "309486"
---
# <a name="prospect-to-cash"></a>Prospect to cash

[!include [banner](../includes/banner.md)]

A solução Prospect to cash fornece sincronização direta entre o Dynamics 365 for Finance and Operations e o Dynamics 365 for Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. Apesar de os dados estarem fluindo entre o Finance and Operations e o Sales, você pode executar atividades de vendas e de marketing no Sales e pode tratar o atendimento da ordem usando o gerenciamento de estoque no Finance and Operations. 

Para obter mais informações sobre a integração Prospect to cash, assista ao vídeo curto no YouTube [Integração do cliente potencial ao pagamento à vista](https://www.youtube.com/watch?v=AVV9x5x-XCg).

Na versão atual, a solução Prospect to cash fornece os seguintes tipos de sincronização direta:

- [Manter contas no Sales e sincronizá-las diretamente do Sales para o Finance and Operations.](accounts-template-mapping-direct.md)
- [Manter produtos no Finance and Operations e sincronizá-los diretamente para o Sales](products-template-mapping-direct.md)
- [Manter contatos no Sales e sincronizá-los diretamente para contatos ou clientes do Finance and Operations](contacts-template-mapping-direct.md)
- [Sincronizar cotação de venda diretamente do Sales para o Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Sincronizar ordens de venda diretamente entre o Sales e o Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizar fatura de venda diretamente do Finance and Operations para o Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos de sistema para Finance and Operations
A integração Prospect to cash tem suporte nas seguintes versões:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (dezembro de 2017).

- Dynamics 365 for Finance and Operations, Enterprise edition (dezembro de 2017) - compilação do aplicativo 7.3.11971.56116 com atualização de plataforma 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise edition (julho de 2017)

- Dynamics 365 for Finance and Operations, Enterprise edition (julho de 2017) - com atualização de plataforma 8 (compilação do aplicativo 7.2.11792.56024 com compilação de plataforma 7.0.4565.16212).
- Os seguintes hotfixes são necessários:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Este hotfix permite a sincronização da ordem de venda do Sales para o Finance and Operations através do recurso de Integração de dados. Também fornece diversos outros aprimoramentos.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Este hotfix permite a sincronização da linha da ordem de venda do Finance and Operations para o Sales através do recurso de Integração de dados.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Este hotfix permite a sincronização da ordem de venda do Finance and Operations para o Sales através do recurso de Integração de dados.

    > [!NOTE]
    > Basta instalar o KB4045570, pois a instalação inclui as alterações dos outros hotfixes. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations versão 1611 (novembro de 2016)

- Dynamics 365 for Finance and Operations versão 1611 (novembro de 2016) com atualização da plataforma 8 ou superior

- Os seguintes hotfixes são necessários:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permite a sincronização da ordem de venda com o Integrador de dados do Finance and Operations para o Sales. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permite a sincronização da linha e do cabeçalho da ordem de venda com o Integrador de dados do Finance and Operations para o Sales.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - É necessário o suporte para integração de prospect to cash através de entidades de dados.
    
    > [!NOTE]
    > Após a instalação dos hotfixes, você deve disparar o seguinte trabalho em lotes do formulário **SalesPopulateProspectToCash**. Este formulário fica oculto, pois você só precisa dele uma vez. Para acessar o formulário, faça logon no ambiente e adicione o seguinte ao URL no endereço do navegador: *&mi=action:SalesPopulateProspectToCash*, por exemplo, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Ao abrir o formulário, clique em OK. Será preenchido um novo campo **LineCreationSequnceNumber** nas tabelas **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** com valores exclusivos e a lista de produtos será atualizada. Isso é necessário para que a integração do Prospect to cash funcione.


## <a name="system-requirements-for-sales"></a>Requisitos do sistema para Sales

Para usar a solução Prospect to cash, instale os seguintes componentes:

- Dynamics 365 for Sales versão 1612 (8.2.1.207) (DB 8.2.1.207) online ou uma versão posterior
- Solução Prospect to cash para o Dynamics 365 for Sales, versão 1.15.0.0 ou uma versão posterior. A solução está disponível para download no AppSource. [Download do Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
