---
title: Configuração da gravação dupla do Lifecycle Services
description: Este tópico explica como configurar uma conexão de gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103560"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuração da gravação dupla do Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico explica como habilitar a gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Pré-requisitos

Você deve concluir a integração da Power Platform conforme descrito nos seguintes tópicos:

+ [Integração do Power Platform - Habilitar durante a implantação do ambiente](../../power-platform/overview.md#enable-during-environment-deployment)
+ [Integração do Power Platform - Configurar depois da implantação do ambiente](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Configurar a gravação dupla para novos ambientes do Dataverse

Siga estas etapas para configurar a gravação dupla da página **Detalhes de ambiente** do LCS:

1. Na página **Detalhes de ambiente**, expanda a seção **Integração da Power Platform**.

2. Selecione o botão **Aplicativo de gravação dupla**.

    ![Integração com o Power Platform](media/powerplat_integration_step2.png)

3. Analise os termos e condições e selecione **Configurar**.

4. Selecione **OK** para continuar.

5. Você pode monitorar o progresso atualizando periodicamente a página de detalhes do ambiente. A configuração geralmente leva 30 minutos ou menos.  

6. Quando a configuração for concluída, uma mensagem informará a você se o processo foi bem-sucedido ou se houve uma falha. Se a configuração falhar, uma mensagem de erro relacionada será exibida. Você deve corrigir qualquer erro antes de passar para a próxima etapa.

7. Selecione **Vincular ao ambiente da Power Platform** para criar um link entre o Dataverse e os bancos de dados do ambiente atual. Isso geralmente leva menos de 5 minutos.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Vincular ao ambiente da Power Platform":::

8. Quando a vinculação for concluída, um hiperlink será exibido. Use a vinculação para entrar na área de administração de gravação dupla no ambiente do Finance and Operations. A partir daí, você pode configurar mapeamentos de entidade.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Configurar a gravação dupla para um ambiente do Dataverse existente

Para configurar a gravação dupla para um ambiente do Dataverse existente, você deve criar um [tíquete de suporte](../../lifecycle-services/lcs-support.md) da Microsoft. O tíquete deve incluir:

+ Sua ID de ambiente do Finance and Operations.
+ O nome do seu ambiente do Lifecycle Services.
+ A ID da organização do Dataverse ou a ID do ambiente da Power Platform a partir do centro de administração da Power Platform. Em seu tíquete, solicite que a ID seja a instância usada para integração da Power Platform.

> [!NOTE]
> Não é possível desvincular ambientes usando o LCS. Para desvincular um ambiente, abra o espaço de trabalho da **Integração de dados** no ambiente do Finance and Operations e selecione **Desvincular**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
