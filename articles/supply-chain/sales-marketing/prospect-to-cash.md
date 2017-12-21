---
title: Prospect to cash
description: "Este tópico fornece uma visão geral da solução Prospect to cash entre o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition e o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 11/17/2017
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
ms.sourcegitcommit: 788e64476094e84eb4d438890776306c05b20582
ms.openlocfilehash: 762699cf68ec8a9df5db20d7dd33bc9248f0a36e
ms.contentlocale: pt-br
ms.lasthandoff: 12/11/2017

---

# <a name="prospect-to-cash"></a>Prospect to cash

[!include[banner](../includes/banner.md)]

A solução Prospect to cash fornece sincronização direta entre o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition e o Microsoft Dynamics 365 for Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. Apesar de os dados estarem fluindo entre o Finance and Operations e o Sales, você pode executar atividades de vendas e de marketing no Sales e pode tratar o atendimento da ordem usando o gerenciamento de estoque no Finance and Operations.

Na versão atual, a solução Prospect to cash fornece os seguintes tipos de sincronização direta:

- [Manter contas no Sales e sincronizá-las diretamente do Sales para o Finance and Operations.](accounts-template-mapping-direct.md)
- [Manter produtos no Finance and Operations e sincronizá-los diretamente para o Sales.](products-template-mapping-direct.md)
- [Manter contatos no Sales e sincronizá-los diretamente para contatos ou clientes do Finance and Operations](contacts-template-mapping-direct.md)
- [Sincronizar cotação de venda diretamente do Sales para o Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Sincronizar ordens de venda diretamente do Finance and Operations para o Sales](sales-order-template-mapping-direct.md)
- [Sincronizar ordens de venda diretamente entre o Sales e o Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizar fatura de venda diretamente do Finance and Operations para o Sales](sales-invoice-template-mapping-direct.md)

Nas versões anteriores, a solução Prospect to cash fornece os seguintes tipos de sincronização não direta:

- [Manter contas no Sales e sincronizá-las para o Finance and Operations.](accounts-template-mapping.md)
- [Manter contatos no Sales e sincronizá-los para o Finance and Operations.](contacts-template-mapping.md)
- [Manter produtos no Finance and Operations e sincronizá-los para o Sales.](products-template-mapping.md)
- [Criar cotações de vendas no Sales e sincronizá-las para o Finance and Operations.](sales-quotation-template-mapping.md)
- [Criar ordens de venda no Finance and Operations e sincronizá-las para o Sales.](sales-order-template-mapping.md)
- [Criar faturas de venda no Finance and Operations e sincronizá-las com o Sales.](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos de sistema para Finance and Operations

Para usar a solução Prospect to cash, instale os seguintes componentes:

### <a name="july-2017"></a>Julho de 2017 

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017) com atualização da plataforma 8 (compilação do aplicativo 7.2.11792.56024 com compilação de plataforma 7.0.4565.16212)
- Os seguintes hotfixes para Finance and Operations:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Este hotfix permite a sincronização da ordem de venda do Sales para o Finance and Operations através do recurso de Integração de dados. Também fornece diversos outros aprimoramentos.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Este hotfix permite a sincronização da linha da ordem de venda do Finance and Operations para o Sales através do recurso de Integração de dados.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Este hotfix permite a sincronização da ordem de venda do Finance and Operations para o Sales através do recurso de Integração de dados.

    > [!NOTE]
    > Basta instalar o KB4045570 pois a instalação inclui as alterações dos outros artigos da Base de Dados de Conhecimento da Microsoft (KBs).

### <a name="november-2016-version-1611"></a>Novembro de 2016 (Versão 1611)

- Atualização da plataforma 8 ou superior do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Novembro de 2016)

- Os seguintes hotfixes para Finance and Operations:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permite a sincronização da ordem de venda com o integrador de dados do Microsoft Dynamics 365 for Finance and Operations para Sales 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permite a sincronização do cabeçalho e da linha da ordem de venda com o Integrador de dados do Microsoft Dynamics 365 for Finance and Operations para Sales
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - É necessário o suporte para integração de prospect to cash através de entidades de dados
    
    > [!NOTE]
    > Após a instalação dos hotfixes você deve disparar o seguinte trabalho em lotes do formulário SalesPopulateProspectToCash. Este formulário fica oculto, pois você só precisa dele uma vez. Para acessá-lo, adicione o seguinte endereço de navegador, quando entrar no ambiente: &mi=action:SalesPopulateProspectToCash https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash no formulário aberto clique em OK.
    Será preenchido um novo campo “LineCreationSequnceNumber” nas tabelas “SalesLine”, “SalesQuotationLine” e “CustInvoiceTrans” com valores exclusivos e será atualizada a lista de produtos. Isso é necessário para que a integração de P2C funcione na versão 7.1


## <a name="system-requirements-for-sales"></a>Requisitos do sistema para Sales

Para usar a solução Prospect to cash, instale os seguintes componentes:

- Versão 1612 (8.2.1.207) (DB 8.2.1.207) online do Microsoft Dynamics 365 for Sales
- Solução Prospect to cash para Microsoft Dynamics 365 for Sales, versão 1.15.0.0 (v15) 

   > [!NOTE]
   >
   > Os modelos com versão 1.0.0.0 e 1.0.0.1 são suportados na solução Prospect to cash para Microsoft Dynamics 365 for Sales, versão 1.14.1.0
   >
   > Os modelos com versão 2.0.0.0 e 2.1.0.0 são suportados na solução Prospect to cash para Microsoft Dynamics 365 for Sales, versão 1.15.0.0

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Instale a solução Prospect to cash para Sales

1. Baixe o [arquivo zip do pacote da solução Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) no CustomerSource.
2. Verifique se o arquivo zip está desbloqueado. Se não, ao tentar instalar o pacote de solução, você receberá a seguinte mensagem de erro: “Nenhum pacote de importação encontrado." Para desbloquear o arquivo zip, clique com o botão direito do mouse nele e selecione **Propriedades**. Em seguida, selecione **Desbloquear**.
3. Descompacte e execute o arquivo **PackageDeployer.exe**.
4. Instale a solução Prospect to cash em sua instância do Sales:

    1. Selecione **Office 365** como o tipo de implantação.
    2. Selecione **Mostrar avançada**.
    3. Para uma instalação rápida, selecione uma região. Se você selecionar **Não sei**, o sistema pesquisará todas as regiões e a instalação demorará mais.
    4. Informe o nome do usuário e a senha de um usuário administrativo que tem os direitos de instalação.

