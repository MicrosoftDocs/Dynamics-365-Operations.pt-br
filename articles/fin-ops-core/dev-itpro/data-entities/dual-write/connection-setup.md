---
title: Orientações sobre configuração da gravação dupla
description: Este tópico descreve os cenários com suporte para configuração de gravação dupla.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 999b37970be1c10fd5e78c3d8ac6c1fb25cad367
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751377"
---
# <a name="guidance-for-dual-write-setup"></a>Orientações sobre configuração da gravação dupla

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

É possível configurar uma conexão de gravação dupla entre um ambiente do Finance and Operations e um ambiente do Dataverse.

+ Um **ambiente do Finance and Operations** fornece a plataforma subjacente para **aplicativos do Finance and Operations** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources).
+ Um **ambiente do Dataverse** fornece a plataforma subjacente para **aplicativos do Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> O módulo de recursos humanos no Dynamics 365 Finance oferece suporte a conexões de gravação dupla, mas o aplicativo Dynamics 365 Human Resources não.

O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente:

+ Para novas instâncias de aplicativos do Finance and Operations, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS). Se você possuir uma licença para a Microsoft Power Platform, receberá um novo ambiente do Dataverse caso o locatário não tenha um.
+ Para aplicativos do Finance and Operations de instâncias existentes, a configuração de uma conexão de gravação dupla começa no ambiente do Finance and Operations.

Antes de iniciar a gravação dupla em uma entidade, você poderá executar uma sincronização inicial para manipular dados existentes em ambos os lados: aplicativos do Finance and Operations e aplicativos do Customer Engagement. Você poderá ignorar a sincronização inicial se não precisar sincronizar dados entre os dois ambientes.

Uma sincronização inicial permite copiar dados existentes de um aplicativo para outro bidirecionalmente. Há vários cenários de configuração, dependendo do ambiente que você já tiver e que tipo de dados existirem neles.

Há suporte para os seguintes cenários de instalação:

+ [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement](#new-new)
+ [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement](#new-existing)
+ [Uma nova instância de aplicativo do Finance and Operations com dados e uma nova instância de aplicativo do Customer Engagement](#new-data-new)
+ [Uma nova instância de aplicativo do Finance and Operations com dados e uma instância existente de aplicativo do Customer Engagement](#new-data-existing)
+ [Uma instância existente de aplicativo do Finance and Operations e uma instância de aplicativo do Customer Engagement](#existing-new)
+ [Uma instância existente de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma nova instância de um aplicativo do Customer Engagement, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md). Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:

- Um novo ambiente vazio do Finance and Operations é provisionado.
- É provisionada uma nova instância vazia de um aplicativo do Customer Engagement, em que a solução principal do CRM está instalada.
- Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.
- Os mapas de tabela estão habilitados para sincronização em tempo real.

Ambos os ambientes estão prontos para sincronização de dados em tempo real.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma instância existente de um aplicativo do Customer Engagement, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md). Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:

- Um novo ambiente vazio do Finance and Operations é provisionado.
- Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.
- Os mapas de tabela estão habilitados para sincronização em tempo real.

Ambos os ambientes estão prontos para sincronização de dados em tempo real.

Para sincronizar os dados existentes do Dataverse com o aplicativo do Finance and Operations, siga as etapas a seguir.

1. Crie uma empresa no aplicativo do Finance and Operations.
2. Adicione a empresa à configuração da conexão de gravação dupla.
3. [Inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.
4. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example) posteriormente neste tópico.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Uma nova instância de aplicativo do Finance and Operations com dados e uma nova instância de aplicativo do Customer Engagement

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma nova instância de um aplicativo do Customer Engagement, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement](#new-new), anteriormente neste tópico. Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.

1. Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.
2. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Uma nova instância de aplicativo do Finance and Operations com dados e uma instância existente de aplicativo do Customer Engagement

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma instância existente de um aplicativo do Customer Engagement, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement](#new-existing), anteriormente neste tópico. Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.

1. Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.
2. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para sincronizar os dados existentes do Dataverse com o aplicativo do Finance and Operations, siga as etapas a seguir.

1. Crie uma empresa no aplicativo do Finance and Operations.
2. Adicione a empresa à configuração da conexão de gravação dupla.
3. [Inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.
4. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Uma instância existente de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement

A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma nova instância de um aplicativo do Customer Engagement ocorre no ambiente do Finance and Operation.

1. [Configurar a conexão do aplicativo do Finance and Operations](enable-dual-write.md).
2. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Uma instância existente de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement

A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma instância existente de um aplicativo do Customer Engagement ocorre no ambiente do Finance and Operation.

1. [Configurar a conexão do aplicativo do Finance and Operations](enable-dual-write.md).
2. Para sincronizar os dados existentes do Dataverse com o aplicativo do Finance and Operations, [inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da ISO com três letras.
3. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="example"></a>Exemplo

Para obter um exemplo, consulte [Como habilitar Customers V3 — Mapa de tabelas de contato](enable-entity-map.md#enable-table-map)

Para obter uma abordagem alternativa baseada em volumes de dados em cada entidade que precise executar a sincronização inicial, consulte [Considerações sobre a sincronização inicial](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]