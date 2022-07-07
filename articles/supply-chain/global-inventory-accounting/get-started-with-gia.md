---
title: Introdução à Contabilidade de estoque global
description: Este artigo descreve como começar com a Contabilidade de estoque global.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cbe6bff6fab96900b8bd4e112a8858363fff86d1
ms.sourcegitcommit: 9870b773a2ea8f5675651199fdbc63ca7a1b4453
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013545"
---
# <a name="get-started-with-global-inventory-accounting"></a>Introdução à Contabilidade de estoque global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

A Contabilidade de estoque global de custos permite realizar múltiplas contabilidades de inventário nos razões da Contabilidade de estoque global. É necessário associar cada razão da Contabilidade de estoque global a uma *convenção*. Uma convenção é uma coleção dos seguintes tipos de políticas de contabilidade:

- Objeto de custo
- Base de medida de entrada
- Suposição de fluxo de custos
- Elemento de custo

> [!NOTE]
> Mesmo depois de ativar a Contabilidade de estoque global, ainda é possível realizar a contabilidade de estoque no Microsoft Dynamics 365 Supply Chain Management, como de costume.

A Contabilidade de estoque global é um suplemento. Para disponibilizar os recursos, é necessário instalá-lo a partir do Lifecycle Services (LCS) Microsoft Dynamics. É possível optar por avaliá-lo em um ambiente de teste antes de ativá-lo para ambientes de produção.

No momento, a Contabilidade de estoque global não permite todos os recursos de gerenciamento de custos que são incorporados ao Supply Chain Management. Portanto, é importante que você avalie se o conjunto de recursos disponível no momento atenderá aos seus requisitos.

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a>Como obter o suplemento da Contabilidade de estoque global

> [!IMPORTANT]
> Para usar a Contabilidade de estoque global, você deve ter um ambiente de alta disponibilidade habilitado para LCS (não um ambiente OneBox). Além disso, você deve estar executando a versão 10.0.19 ou posterior do Supply Chain Management.

### <a name="supply-chain-management-version-10019-to-10026"></a>Supply Chain Management versão 10.0.19 a 10.0.26

Para instalar a Contabilidade de Estoque Global para Supply Chain Management versão 10.0.19 a 10.0.26, comece [instalando o suplemento](#install). Depois, envie a ID do ambiente do LCS e o nome da empresa por email para a [Equipe da Contabilidade de estoque global](mailto:GlobalInvAccount@microsoft.com). A equipe enviará a você um email de acompanhamento que contém os pontos de extremidade do serviço Contabilidade de Estoque Global.

### <a name="supply-chain-management-version-10027-and-later"></a>Supply Chain Management versão 10.0.27 ou posterior

Para instalar a Contabilidade de Estoque Global para Supply Chain Management versão 10.0.27 e posterior, basta [instalar o suplemento](#install). Para essas versões do Supply Chain Management, os pontos de extremidade do serviço Contabilidade de Estoque Global serão configurados automaticamente, para que você não precise encontrá-los manualmente. Se você tiver algum problema ao configurar o suplemento, entre em contato com a [Equipe da Contabilidade de estoque global](mailto:GlobalInvAccount@microsoft.com).

## <a name="licensing"></a>Licenciamento

A Contabilidade de estoque global é licenciada com os recursos padrão de contabilidade de estoque que estão disponíveis para o Supply Chain Management. Não é necessário comprar uma licença adicional para usar a Contabilidade de Estoque Global.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="set-up-microsoft-power-platform-integration"></a>Configurar integração do Microsoft Power Platform

Antes de habilitar a funcionalidade de suplemento, você deve se integrar ao Microsoft Power Platform seguindo essas etapas.

1. Abra o ambiente LCS ao qual deseja adicionar o serviço.
1. Acesse **Detalhes completos**.
1. Na seção **Integração do Power Platform**, selecione **Configurar**.
1. Na caixa de diálogo **Configuração do ambiente do Power Platform**, marque a caixa de seleção e selecione **Configuração**. Normalmente, a configuração leva entre 60 e 90 minutos.
1. Após a configuração do ambiente do Microsoft Power Platform ser concluída, a página mostra o nome do seu ambiente. Além disso, a seção **Integração do Power Platform** mostra a afirmação: "A configuração de ambiente do Power Platform foi concluída." A Contabilidade de estoque global não requer um aplicativo de gravação dupla.

Para obter mais informações, consulte a página [Habilitar após a implantação do ambiente](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="install-the-add-in"></a><a name="install"></a>Instalar o suplemento

Siga estas etapas para instalar o suplemento para que você possa usar a Contabilidade de estoque global.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index).
1. Abra o ambiente LCS ao qual deseja adicionar o serviço.
1. Acesse **Detalhes completos**.
1. Acesse **Integração do Power Platform** e selecione **Configuração**.
1. Na caixa de diálogo **Configuração do ambiente do Power Platform**, marque a caixa de seleção e selecione **Configuração**. Normalmente, a configuração leva entre 60 e 90 minutos.
1. Depois de concluir a configuração do ambiente do Microsoft Power Platform, entre no [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com) e instale o suplemento da Contabilidade de Estoque Global seguindo estas etapas:
   1. Selecione o ambiente em que deseja instalar o suplemento.
   1. Selecione **Aplicativos do Dynamics 365**.
   1. Selecione **Instalar aplicativo**.
   1. Selecione **Contabilidade de Estoque Global do Dynamics 365**.
   1. Selecione **Avançar** para instalar.
1. Volte para o ambiente do LCS. Na Guia Rápida **Complementos do ambiente**, selecione **Instalar um novo complemento**.
1. Selecione **Contabilidade de estoque global**.
1. Acompanhe o guia de instalação e concorde com os termos e condições.
1. Selecione **Instalar**.
1. Na Guia Rápida **Suplementos do ambiente**, você verá que o Contabilidade de estoque global está sendo instalado. Após alguns minutos, o status deve mudar de *Instalando* para *Instalado*. (Talvez seja necessário atualizar a página para ver essa alteração.) Nesse momento, a Contabilidade de estoque global já está pronto para uso.

Se o idioma padrão da sua instalação do Dataverse não for inglês, siga estas etapas:
1. Acesse **Configurações avançadas \> Administração \> Idiomas**.
1. Selecione *Inglês* (*LanguageCode = 1033*) e selecione **Aplicar**.

## <a name="set-up-the-integration"></a>Configurar a integração

Siga essas etapas para configurar a integração entre a Contabilidade de estoque global e o Supply Chain Management.

1. Entre no Supply Chain Management.
1. Acesse **Administração do sistema \> Gerenciamento de Recursos**.
1. Selecione **Verificar se há atualizações**.
1. Na guia **Tudo**, pesquise o recurso denominado *(Versão preliminar) Contabilidade de estoque global*.
1. Selecione **Habilitar agora**.
1. Acesse **Contabilidade de estoque global \> Configuração \> Parâmetros contábeis \> Integrações de parâmetros**.
1. Dependendo de qual versão do Supply Chain Management você está executando, execute uma das seguintes etapas:
    - **Supply Chain Management versão 10.0.19 a 10.0.26**: nos campos **Ponto de extremidade do serviço de dados** e **Ponto de extremidade de contabilidade de estoque global**, insira as URLs que foram enviadas a você por email da Equipe da Contabilidade de estoque global (consulte também [Como obter o suplemento da Contabilidade de estoque global](#sign-up)).
    - **Supply Chain Management versão 10.0.27 ou mais recente**: como não é preciso inserir os pontos de extremidade, você pode pular esta etapa.

A Contabilidade de estoque global está pronta para uso.
