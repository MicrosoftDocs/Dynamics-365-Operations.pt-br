---
title: Importar versões atualizadas de configurações de ER
description: Este artigo explica como importar versões atualizadas das configurações de relatório eletrônico (ER) do repositório global do serviço de configuração.
author: kfend
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
ms.openlocfilehash: 0eef9c9a112fd58a43f6c3a85163ccf44bea3d61
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292636"
---
# <a name="import-updated-versions-of-er-configurations"></a>Importar versões atualizadas de configurações de ER

[!include [banner](../includes/banner.md)]

Os [repositórios](general-electronic-reporting.md#Repository) de relatórios eletrônicos (ER) são usados para compartilhar [configurações de ER](general-electronic-reporting.md#Configuration). Você pode [importar](download-electronic-reporting-configuration-lcs.md) configurações de ER de diferentes repositórios para sua instância do Microsoft Dynamics 365 Finance. Quando você importa configurações de ER, [os provedores de configuração](general-electronic-reporting.md#Provider) podem publicar novos repositórios de versões para que eles sejam compartilhados.

Este artigo explica como importar versões atualizadas de configurações de ER do repositório global do serviço de configuração. Para obter mais informações, consulte [Microsoft Dynamics 365 Finance - Regulatory services, serviço de configuração](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>Examinar as versões atualizadas disponíveis

1. Entre no Finance usando uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Importar atualizações de versões de configurações**.

    ![Página Configurações de localização.](./media/er-download-updated-versions-global-repo1.png)

4. Na caixa de diálogo **Importar atualizações de versões de configurações de relatório eletrônico**, no campo **Modo de execução**, selecione **Mostrar somente as atualizações disponíveis**. Em seguida, selecione **OK**. 

    ![Campo de modo de execução definido como Mostrar somente as atualizações disponíveis.](./media/er-download-updated-versions-global-repo2.png)

5. Examine as mensagens recebidas. Essas mensagens fornecem as seguintes informações sobre as configurações de ER na instância atual do Finance e uma comparação com o conteúdo do repositório global:

    - O número total de configurações de ER
    - As configurações de ER que não estão presentes no repositório global
    - As configurações de ER cuja versão mais recente já está disponível na instância atual do Finance (para ver a lista completa dessas configurações de ER, selecione o link **Detalhes da mensagem**.)

        ![Mensagem "As versões mais recentes das configurações a seguir já foram importadas" e detalhes da mensagem](./media/er-download-updated-versions-global-repo3.png)

    - As configurações de ER cuja versão mais recente está disponível no repositório global e pode ser importada para a instância atual do Finance (para ver a lista completa dessas configurações de ER, selecione o link **Detalhes da mensagem**.)

        ![Mensagem "Atualizações disponíveis" e detalhes da mensagem](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>Importar as versões atualizadas disponíveis

1. Entre no Finance usando uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Importar atualizações de versões de configurações**.
4. Na caixa de diálogo **Importar atualizações de versões de configurações de relatório eletrônico**, no campo **Modo de execução**, selecione **Importar atualizações mais recentes** para importar as versões mais recentes das configurações de ER do repositório global para a instância atual do Finance.
5. Para programar um trabalho em lotes para a importação, na FastTab **Executar em segundo plano**, defina a opção **Processamento em lotes** como **Sim**. Se quiser repetir a importação periodicamente, configure a recorrência necessária.

    ![Campo Modo de execução definido como Importar atualizações mais recentes.](./media/er-download-updated-versions-global-repo5.png)

6. Selecione **OK**.
7. Para saber quais versões de configuração foram importadas, siga uma destas etapas:

    - Se você executar a importação interativamente em vez de usar um trabalho em lotes, examine as mensagens recebidas.

        ![Mensagens recebidas durante uma execução de importação interativa.](./media/er-download-updated-versions-global-repo6.png)

    - Se você executar a importação no modo de lotes, siga estas etapas:

        1. Acesse **Comum** \> **Consultas** \> **Trabalhos em lotes** \> **Meus trabalhos em lotes**.
        2. Encontre e selecione o trabalho **Importar atualizações de versões de configurações de relatório eletrônico** e, no Painel de Ação, na guia **Trabalho em lotes**, selecione **Histórico de trabalho em lotes** para ver o histórico de trabalho.
        3. Na página **Histórico de trabalho em lotes**, selecione **Log**. Em seguida, na mensagem recebida, selecione o link **Detalhes da mensagem** para ver o log do trabalho.

        ![Log do trabalho.](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> Não recomendamos agendar um trabalho em lotes recorrente para importar versões atualizadas das configurações de ER diretamente do repositório global para um ambiente de produção, pois as versões importadas estarão disponíveis imediatamente para uso. Em vez disso, use esta abordagem para implantar versões de configurações de ER em um ambiente de área restrita. Elas poderão ser avaliadas no ambiente de área restrita antes de serem implantadas em um ambiente de produção.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Baixar configurações ER do repositório global de serviço de configuração](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
