---
title: Implantar uma solução IoT no Azure
description: O Sensor Data Intelligence usa dados de sensores que estão conectados ao Microsoft Azure. Este artigo explica como implantar uma solução de Internet das Coisas (IoT) na sua assinatura do Azure.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 284aba91aa436ed1dfc02b5a93b4358ffc518017
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428299"
---
# <a name="deploy-an-iot-solution-on-azure"></a>Implantar uma solução IoT no Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

O Sensor Data Intelligence usa dados de sensores que estão conectados ao Microsoft Azure. Para habilitar o Azure a recuperar dados dos sensores e compartilhá-los com o Dynamics 365 Supply Chain Management, você deve implantar uma solução de Internet das Coisas (IoT) na sua assinatura do Azure. O diagrama arquitetônico a seguir fornece uma visão geral da solução e dos componentes.

![Diagrama arquitetônico do Sensor Data Intelligence.](media/sdi-architecture.png "Diagrama arquitetônico do Sensor Data Intelligence")

Siga estas etapas para implantar os recursos necessários no Azure.

1. Entre no Supply Chain Management como administrador.
1. Vá para **Administração do sistema \> Configuração \> Sensor Data Intelligence \> Implantar e conectar recursos do Azure** para abrir o assistente de implantação.
1. Na página **Bem-vindo**, leia as informações e, em seguida, selecione **Avançar**.
1. Na página **Implantar a solução IoT de exemplo no Azure**, leia as informações e, na seção **Instruções**, selecione **Implantar**.
1. Uma nova guia do navegador é aberta, e você é levado ao portal do Azure para que possa implantar os recursos do Azure. Se solicitado, faça login usando as credenciais da sua assinatura do Azure.
1. Na página **Implantação personalizada**, no campo **Assinatura**, selecione sua assinatura.
1. No campo **Grupo de recursos**, selecione **Criar novo** para criar um grupo de recursos para os componentes do Azure que serão implantados.
1. Na caixa de diálogo suspensa exibida, no campo **Nome**, digite um nome para o novo grupo de recursos (por exemplo, *IoT-demo*). Em seguida, selecione **OK**.
1. Defina os seguintes campos:

    - **Grupo de recursos** – Selecione o grupo de recursos que você acabou de criar.
    - **Região** – Selecione uma região, de preferência a região em que seu ambiente de Supply Chain Management é implantado. Tenha em mente que as regiões do Azure têm preços diferentes. Você pode exibir os custos previstos para a sua região usando a [Calculadora de preços do Sensor Data Intelligence](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **URL do ambiente do Supply Chain Management** – Insira o URL do seu ambiente do Supply Chain Management.
    - **Reusar Hub IoT do Azure existente** – Deixe esta caixa de seleção desmarcada.

1. Selecione **Próximo: Revisar + Criar**.
1. Na página **Implantação personalizada**, verifique se a validação foi aprovada e selecione **Criar**.
1. A página **Implantação está em andamento** controla o andamento da implantação. O processo de implantação pode levar até 30 minutos. Quando a página **Implantação está em andamento** indicar que a implantação foi concluída, selecione o link para o nome do grupo de recursos para abrir uma página que mostra a lista de recursos que são implantados no grupo.
1. Na lista de recursos, localize o registro no qual o campo **Tipo** está definido como *Identidade gerenciada*. Na coluna **Nome**, selecione o nome para abrir a página de detalhes do recurso.
1. Copie o valor no campo **ID do cliente** (por exemplo, selecionando o botão **Copiar para a área de transferência**).
1. Volte para a guia do navegador em que o Supply Chain Management está sendo executado, *mas não feche a guia do portal do Azure*. A página do assistente **Implantar a solução IoT de exemplo para o Azure** ainda deve estar aberta. 
1. Selecione **Avançar**.
1. Na página **Conectar recursos do Azure**, no campo **ID do cliente do aplicativo Azure AD**, cole o valor do **ID do cliente** copiado.
1. Volte para a guia do navegador em que o portal do Azure está aberto, *mas não feche a guia do Supply Chain Management*. A página de detalhes do recurso ainda deve estar aberta.
1. Selecione o botão **Voltar** do navegador para retornar à lista de recursos no novo grupo de recursos.
1. Na lista de recursos, localize o registro no qual o campo **Tipo** está definido como *Cache do Azure para Redis*. Na coluna **Nome**, selecione o nome para abrir a página de detalhes do recurso.
1. No painel de navegação esquerdo, selecione **Chaves de acesso**.
1. Na página **Chaves de acesso**, copie o valor mostrado para a **Cadeia de conexão principal (StackExchange.Redis)** (por exemplo, selecionando o botão **Copiar para a área de transferência**).
1. Volte para a guia do navegador em que o Supply Chain Management está sendo executado. A página **Conectar recursos do Azure** ainda deve estar aberta.
1. No campo **Cadeia de conexão do armazenamento de métricas do Redis**, cole o valor da **Cadeia de conexão principal (StackExchange.Redis)** que você copiou.
1. Selecione **Concluir**.

Os recursos do Azure para Sensor Data Intelligence agora estão implantados na sua assinatura do Azure.

> [!NOTE]
> A qualquer momento, você pode exibir ou editar as informações de conexão salvas no Supply Chain Management abrindo a página **Parâmetros do Sensor Data Intelligence**. Para obter mais informações, consulte [Parâmetros do Sensor Data Intelligence](sdi-parameters.md).
