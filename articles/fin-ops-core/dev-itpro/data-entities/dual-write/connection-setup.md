---
title: Cenários com suporte para configuração de gravação dupla
description: Este tópico descreve os cenários com suporte para configuração de gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b4f69e7933bc5a50cccad6911c99cf08d2768578
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818587"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>Cenários com suporte para configuração de gravação dupla

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

É possível configurar uma conexão de gravação dupla entre um ambiente do Finance and Operations e um ambiente do Common Data Service.

+ Um ambiente do **Finance and Operations** fornece a plataforma subjacente para aplicativos **Finance and Operations** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).
+ Um **ambiente do Common Data Service** fornece a plataforma subjacente para **aplicativos baseados em modelo no Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).

>[!IMPORTANT]
>Recursos humanos no Finance and Operations oferece suporte a conexões de gravação dupla, mas o aplicativo Dynamics 365 Human Resources não.

O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente.

+ Para novas instâncias de aplicativos do Finance and Operations, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS). Se você possuir uma licença para a Power Platform, receberá um novo ambiente do Common Data Service caso o locatário não tenha um.
+ Para aplicativos do Finance and Operations de instâncias existentes, a configuração de uma conexão de gravação dupla começa no ambiente do Finance and Operations.

Há suporte para os seguintes cenários de instalação:

+ [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo](#new-new)
+ [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo](#new-existing)
+ [Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma nova instância de aplicativo baseado em modelo](#new-demo-new)
+ [Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma instância existente de aplicativo baseado em modelo](#new-demo-existing)
+ [Uma instância existente de aplicativo do Finance and Operations e uma instância nova ou existente de aplicativo baseado em modelo](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma nova instância de um aplicativo baseado em modelo no Dynamics 365, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md). Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:

- Um novo ambiente vazio do Finance and Operations é provisionado.
- É provisionada uma nova instância vazia de um aplicativo baseado em modelo, em que a solução principal do CRM está instalada.
- Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.
- Os mapas de entidade estão habilitados para sincronização em tempo real.

Ambos os ambientes estão prontos para sincronização de dados em tempo real.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma instância existente de um aplicativo baseado em modelo no Dynamics 365, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md). Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:

- Um novo ambiente vazio do Finance and Operations é provisionado.
- Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.
- Os mapas de entidade estão habilitados para sincronização em tempo real.

Ambos os ambientes estão prontos para sincronização de dados em tempo real.

Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.

1. Crie uma empresa no aplicativo do Finance and Operations.
2. Adicione a empresa à configuração da conexão de gravação dupla.
3. [Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.

Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma nova instância de aplicativo baseado em modelo

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma nova instância de um aplicativo baseado em modelo no Dynamics 365, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo](#new-new) anteriormente neste tópico. Quando a configuração da conexão estiver concluída, para sincronizar os dados de demonstração com o aplicativo baseado em modelo, siga as etapas a seguir.

1. Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.
2. Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma instância existente de aplicativo baseado em modelo

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma instância existente de um aplicativo baseado em modelo no Dynamics 365, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo](#new-existing) anteriormente neste tópico. Quando a configuração da conexão estiver concluída, para sincronizar os dados de demonstração com o aplicativo baseado em modelo, siga as etapas a seguir.

1. Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.
2. Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.

Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.

1. Crie uma empresa no aplicativo do Finance and Operations.
2. Adicione a empresa à configuração da conexão de gravação dupla.
3. [Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.

Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>Uma instância existente de aplicativo do Finance and Operations e uma instância nova ou existente de aplicativo baseado em modelo

A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma instância nova ou existente de um aplicativo baseado em modelo no Dynamics 365 ocorre no ambiente do Finance and Operation.

1. Configure a conexão do aplicativo do Finance and Operations.
2. Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, [inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da ISO com três letras.

Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.
