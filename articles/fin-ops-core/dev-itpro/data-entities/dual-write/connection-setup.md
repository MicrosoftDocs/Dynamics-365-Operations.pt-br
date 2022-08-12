---
title: Orientações sobre configuração da gravação dupla
description: Este artigo descreve os cenários com suporte para configuração de gravação dupla.
author: RamaKrishnamoorthy
ms.date: 06/28/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 15dfb609b5e25b4faf2b913cc2310df71c88a74d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111239"
---
# <a name="guidance-for-dual-write-setup"></a>Orientações sobre configuração da gravação dupla

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



É possível configurar uma conexão de gravação dupla entre um ambiente de finanças e operações e um ambiente do Dataverse.

+ Um **ambiente de finanças e operações** fornece a plataforma subjacente para **aplicativos de finanças e operações** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources).
+ Um **ambiente do Dataverse** fornece a plataforma subjacente para **aplicativos do Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).


> [!IMPORTANT]
> O módulo de recursos humanos no Dynamics 365 Finance oferece suporte a conexões de gravação dupla, mas o aplicativo Dynamics 365 Human Resources não.

O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente:

+ Para novas instâncias de aplicativos de finanças e operações, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS). Se você possuir uma licença para a Microsoft Power Platform, receberá um novo ambiente do Dataverse caso o locatário não tenha um.
+ Para instâncias existentes de aplicativos de finanças e operações, a configuração de uma conexão de gravação dupla começa no ambiente de finanças e operações.

Antes de iniciar a gravação dupla em uma entidade, você poderá executar uma sincronização inicial para manipular dados existentes em ambos os lados: aplicativos de finanças e operações e aplicativos de engajamento do cliente. Você poderá ignorar a sincronização inicial se não precisar sincronizar dados entre os dois ambientes.

Uma sincronização inicial permite copiar dados existentes de um aplicativo para outro bidirecionalmente. Há vários cenários de configuração, dependendo do ambiente que você já tiver e que tipo de dados existirem neles.

Há suporte para os seguintes cenários de instalação:

+ [Uma nova instância de aplicativo de finanças e operações e uma nova instância de aplicativo de engajamento do cliente](#new-new)
+ [Uma nova instância de aplicativo de finanças e operações e uma instância de aplicativo existente de engajamento do cliente](#new-existing)
+ [Uma nova instância de aplicativo de finanças e operações com dados e uma nova instância de aplicativo de engajamento do cliente](#new-data-new)
+ [Uma nova instância de aplicativo de finanças e operações com dados e uma instância de aplicativo existente de engajamento do cliente](#new-data-existing)
+ [Uma instância de aplicativo existente de finanças e operações e uma nova instância de aplicativo de engajamento do cliente](#existing-new)
+ [Uma instância de aplicativo existente de finanças e operações e uma instância existente de aplicativo de engajamento do cliente](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Uma nova instância de aplicativo de finanças e operações e uma nova instância de aplicativo de engajamento do cliente

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo de finanças e operações sem dados e uma nova instância de um aplicativo de engajamento do cliente, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md). Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:

- Um novo ambiente de finanças e operações vazio é provisionado.
- É provisionada uma nova instância vazia de um aplicativo do Customer Engagement, em que a solução principal do CRM está instalada.
- Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.
- Os mapas de tabela estão habilitados para sincronização em tempo real.

Ambos os ambientes estão prontos para sincronização de dados em tempo real.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Uma nova instância de aplicativo de finanças e operações e uma instância de aplicativo existente do engajamento do cliente

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo de finanças e operações sem dados e uma instância existente de um aplicativo de engajamento do cliente, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md). Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:

- Um novo ambiente de finanças e operações vazio é provisionado.
- Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.
- Os mapas de tabela estão habilitados para sincronização em tempo real.

Ambos os ambientes estão prontos para sincronização de dados em tempo real.

Para sincronizar os dados existentes do Dataverse com o aplicativo de finanças e operações, siga as etapas a seguir.

1. Crie uma nova empresa no aplicativo de finanças e operações.
2. Adicione a empresa à configuração da conexão de gravação dupla.
3. [Inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.
4. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example) posteriormente neste artigo.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Uma nova instância de aplicativo de finanças e operações com dados e uma nova instância de aplicativo de engajamento do cliente

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo de finanças e operações com dados e uma nova instância de um aplicativo de engajamento do cliente, siga as etapas na seção [Uma nova instância de aplicativo de finanças e operações e uma nova instância de aplicativo de engajamento do cliente](#new-new), anteriormente neste artigo. Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.

1. Abra o aplicativo de finanças e operações na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.
2. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Uma nova instância de aplicativo de finanças e operações com dados e uma instância de aplicativo existente de engajamento do cliente

Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo de finanças e operações com dados e uma instância existente de um aplicativo de engajamento do cliente, siga as etapas na seção [Uma nova instância de aplicativo de finanças e operações e uma instância de aplicativo existente de engajamento do cliente](#new-existing), anteriormente neste artigo. Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.

1. Abra o aplicativo de finanças e operações na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.
2. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para sincronizar os dados existentes do Dataverse com o aplicativo de finanças e operações, siga as etapas a seguir.

1. Crie uma nova empresa no aplicativo de finanças e operações.
2. Adicione a empresa à configuração da conexão de gravação dupla.
3. [Inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.
4. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Uma instância de aplicativo existente de finanças e operações e uma nova instância de aplicativo de engajamento do cliente

A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo de finanças e operações e uma nova instância de um aplicativo de engajamento do cliente ocorre no ambiente de finanças e operações.

1. [Configure a conexão no aplicativo de finanças e operações](enable-dual-write.md).
2. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Uma instância de aplicativo existente de finanças e operações e uma instância de aplicativo existente de engajamento do cliente

A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo de finanças e operações e uma instância existente de um aplicativo de engajamento do cliente ocorre no ambiente de finanças e operações.

1. [Configure a conexão no aplicativo de finanças e operações](enable-dual-write.md).
2. Para sincronizar os dados existentes do Dataverse com o aplicativo de finanças e operações, [inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da ISO com três letras.
3. Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.

Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).

## <a name="example"></a>Exemplo

Para obter um exemplo, consulte [Como habilitar Customers V3 — Mapa de tabelas de contato](enable-entity-map.md#enable-table-map)

Para obter uma abordagem alternativa baseada em volumes de dados em cada entidade que precise executar a sincronização inicial, consulte [Considerações sobre a sincronização inicial](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
