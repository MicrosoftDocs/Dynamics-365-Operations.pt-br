---
title: Prospect to cash
description: Este tópico fornece uma visão geral da solução Prospect to cash entre o Dynamics 365 Supply Chain Management e o Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b2f2f7d95d3f0e6bd774c43024836aac1f729abd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977629"
---
# <a name="prospect-to-cash"></a>Cliente potencial ao pagamento à vista

[!include [banner](../includes/banner.md)]

A solução Prospect to cash fornece sincronização direta entre o Dynamics 365 Supply Chain Management e o Dynamics 365 Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas. Enquanto os dados estiverem fluindo, você poderá executar atividades de vendas e marketing no Sales, bem como poderá tratar do atendimento da ordem usando o gerenciamento de estoque no Supply Chain Management. 

Para obter mais informações sobre a integração Prospect to cash, assista ao vídeo curto no YouTube [Integração do cliente potencial ao pagamento à vista](https://www.youtube.com/watch?v=AVV9x5x-XCg).

Na versão atual, a solução Prospect to cash fornece os seguintes tipos de sincronização direta:

- [Sincronizar contas diretamente do Sales com clientes no Supply Chain Management](accounts-template-mapping-direct.md)
- [Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales](products-template-mapping-direct.md)
- [Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management](contacts-template-mapping-direct.md)
- [Sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management](sales-quotation-template-mapping-sales-fin.md)
- [Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>Requisitos de sistema do Supply Chain Management
A integração Prospect to cash tem suporte nas seguintes versões:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (dezembro de 2017).

- Dynamics 365 for Finance and Operations, Enterprise edition (dezembro de 2017) - compilação do aplicativo 7.3.11971.56116 com atualização de plataforma 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise edition (julho de 2017)

- Dynamics 365 for Finance and Operations, Enterprise edition (julho de 2017) - com atualização de plataforma 8 (compilação do aplicativo 7.2.11792.56024 com compilação de plataforma 7.0.4565.16212).
- Os seguintes hotfixes são necessários:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Esse hotfix permite a sincronização da ordem de venda do Sales para o Supply Chain Management por meio do recurso Integração de Dados. Também fornece diversos outros aprimoramentos.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esse hotfix permite a sincronização da linha da ordem de venda do Supply Chain Management para o Sales por meio do recurso Integração de Dados.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esse hotfix permite a sincronização da ordem de venda do Supply Chain Management para o Sales por meio do recurso Integração de Dados.

    > [!NOTE]
    > Basta instalar o KB4045570, pois a instalação inclui as alterações dos outros hotfixes. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations versão 1611 (novembro de 2016)

- Dynamics 365 for Finance and Operations versão 1611 (novembro de 2016) com atualização da plataforma 8 ou superior

- Os seguintes hotfixes são necessários:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** – Permite a sincronização da ordem de venda com o Integrador de dados do Supply Chain Management com o Sales. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** – Permite a sincronização do cabeçalho e da linha da ordem de venda com o Integrador de dados do Supply Chain Management com o Sales.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - É necessário o suporte para integração de prospect to cash através de entidades de dados.
    
    > [!NOTE]
    > Após a instalação dos hotfixes, você deve disparar o seguinte trabalho em lotes do formulário **SalesPopulateProspectToCash**. Este formulário fica oculto, pois você só precisa dele uma vez. Para acessar o formulário, faça logon no ambiente e adicione o seguinte ao URL no endereço do navegador: *&mi=action:SalesPopulateProspectToCash*, por exemplo, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Ao abrir o formulário, clique em OK. Será preenchido um novo campo **LineCreationSequnceNumber** nas tabelas **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** com valores exclusivos e a lista de produtos será atualizada. Isso é necessário para que a integração do Prospect to cash funcione.


## <a name="system-requirements-for-sales"></a>Requisitos do sistema para Sales

Para usar a solução Prospect to cash, instale os seguintes componentes:

- Dynamics 365 Sales versão 1612 (8.2.1.207) (DB 8.2.1.207) online ou uma versão posterior
- Solução Prospect to cash para Dynamics 365 Sales, versão 1.15.0.0 ou uma versão posterior. A solução está disponível para download no AppSource. [Download do Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
