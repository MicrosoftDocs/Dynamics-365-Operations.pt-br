---
title: Configuração da gravação dupla do Lifecycle Services
description: Este artigo explica como configurar uma conexão de gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: laswenka
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: dda0b20492a109e4c3781db520ac19c325e0b403
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289168"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuração da gravação dupla do Lifecycle Services

[!include [banner](../../includes/banner.md)]



Este artigo explica como habilitar a gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Pré-requisitos

Os clientes devem concluir a integração da Power Platform conforme descrito nos tópicos a seguir:

- Se você ainda não usa o Microsoft Power Platform e deseja expandir seus ambientes do aplicativo de finanças e operações adicionando recursos de plataforma, consulte [Integração do Power Platform - Habilitar durante a implantação do ambiente](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Se você já tiver ambientes do Dataverse e do Power Platform e deseja conectá-los a ambientes do aplicativo de finanças e operações, consulte [Integração do Power Platform - Habilitar após a implantação do ambiente](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Configurar a gravação dupla para ambientes novos ou existentes do Dataverse

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

8. Quando a vinculação for concluída, um hiperlink será exibido. Use o link para acessar a área de administração de gravação dupla no ambiente do aplicativo de finanças e operações. A partir daí, você pode configurar mapeamentos de entidade.

## <a name="linking-mismatch"></a>Incompatibilidade de vinculação

É possível que seu ambiente de gravação dupla esteja vinculado a uma instância do Dataverse enquanto o LCS não está configurado para integração da Power Platform. Essa incompatibilidade de vinculação pode causar um comportamento inesperado. É recomendável que os detalhes do ambiente do LCS correspondam ao que você está conectado em gravação dupla para que a mesma conexão possa ser usada por eventos de negócios, tabelas virtuais e suplementos.

Se o ambiente tiver uma incompatibilidade de vinculação, o LCS exibirá um aviso semelhante ao exemplo a seguir na página de detalhes do seu ambiente: "A Microsoft detectou que seu ambiente está vinculado por meio de gravação dupla a um destino diferente do especificado na integração do Power Platform, que não é recomendado."

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Vínculo de integração do Power Platform incompatível.":::

Se você receber esse aviso, tente uma das seguintes soluções:

- Se o seu ambiente do LCS nunca foi configurado para integração da Power Platform, você pode se conectar à instância do Dataverse que está configurada em gravação dupla seguindo as instruções neste artigo.
- Se o seu ambiente do LCS já estiver configurado para integração da Power Platform, você deve desvincular a gravação dupla e reconectá-lo à especificada pelo LCS usando o [Cenário: redefinir ou alterar a vinculação](relink-environments.md#scenario-reset-or-change-linking).

No passado, uma opção de ticket de suporte manual estava disponível, mas isso foi antes da opção 1 acima existir.  A Microsoft não oferece mais suporte a solicitações de revinculação manuais por meio de tickets de suporte.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

