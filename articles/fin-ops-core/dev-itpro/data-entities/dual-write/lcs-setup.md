---
title: Configuração da gravação dupla do Lifecycle Services
description: Este tópico explica como configurar uma conexão de gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2cfe6d882c5de763164ddb4a344cba2991c88783
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416642"
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

    ![Integração com o Power Platform.](media/powerplat_integration_step2.png)

3. Analise os termos e condições e selecione **Configurar**.

4. Selecione **OK** para continuar.

5. Você pode monitorar o progresso atualizando periodicamente a página de detalhes do ambiente. A configuração geralmente leva 30 minutos ou menos.  

6. Quando a configuração for concluída, uma mensagem informará a você se o processo foi bem-sucedido ou se houve uma falha. Se a configuração falhar, uma mensagem de erro relacionada será exibida. Você deve corrigir qualquer erro antes de passar para a próxima etapa.

7. Selecione **Vincular ao ambiente da Power Platform** para criar um link entre o Dataverse e os bancos de dados do ambiente atual. Isso geralmente leva menos de 5 minutos.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Vincular ao ambiente da Power Platform.":::

8. Quando a vinculação for concluída, um hiperlink será exibido. Use a vinculação para entrar na área de administração de gravação dupla no ambiente do Finance and Operations. A partir daí, você pode configurar mapeamentos de entidade.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Configurar a gravação dupla para um ambiente do Dataverse existente

Para configurar a gravação dupla para um ambiente do Dataverse existente, você deve criar um [tíquete de suporte](../../lifecycle-services/lcs-support.md) da Microsoft. O tíquete deve incluir:

+ Sua ID de ambiente do Finance and Operations.
+ O nome do seu ambiente do Lifecycle Services.
+ A ID da organização do Dataverse ou a ID do ambiente da Power Platform a partir do centro de administração da Power Platform. Em seu tíquete, solicite que a ID seja a instância usada para integração da Power Platform.

> [!NOTE]
> Não é possível desvincular ambientes usando o LCS. Para desvincular um ambiente, abra o espaço de trabalho da **Integração de dados** no ambiente do Finance and Operations e selecione **Desvincular**.

## <a name="linking-mismatch"></a>Incompatibilidade de vinculação

É possível que o ambiente do LCS esteja vinculado a uma instância do Dataverse e o ambiente de gravação dupla esteja vinculado a outra instância do Dataverse. Essa incompatibilidade de vinculação pode causar um comportamento inesperado e acabar enviando dados ao ambiente errado. O ambiente recomendado para a gravação dupla é aquele criado como parte da integração do Power Platform e, no longo prazo, essa será a única maneira de estabelecer um vínculo entre ambientes.

Se o ambiente tiver uma incompatibilidade de vinculação, o LCS exibirá um aviso na página de detalhes do ambiente, semelhante a "A Microsoft detectou que seu ambiente está vinculado por meio de gravação dupla a um destino diferente do especificado na integração do Power Platform, o que não é recomendado":

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Vínculo de integração do Power Platform incompatível.":::

Se você encontrar esse erro, há duas opções, com base nas suas necessidades:

+ [Desvincular e vincular novamente os ambientes de gravação dupla (redefinir ou alterar a vinculação)](relink-environments.md#scenario-reset-or-change-linking) conforme especificado na página de detalhes do ambiente do LCS. Essa é a opção ideal, pois você pode executá-la sem o suporte da Microsoft.  
+ Se quiser manter seu vínculo em gravação dupla, você poderá pedir ajuda ao suporte da Microsoft para alterar a integração do Power Platform a fim de usar o ambiente do Dataverse existente, conforme documentado na seção anterior.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
