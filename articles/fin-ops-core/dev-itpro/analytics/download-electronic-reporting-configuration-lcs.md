---
title: Baixar configurações do Relatório eletrônico no Lifecycle Services
description: Este artigo explica como baixar configurações de ER (relatório eletrônico) do Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace
ms.openlocfilehash: f48dd14bc3009550d78bd71db030c172d2ef6450
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277806"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Baixar configurações do Relatório eletrônico no Lifecycle Services

[!include [banner](../includes/banner.md)]

Este artigo explica como baixar a versão mais recente das [configurações de relatório eletrônico (ER)](general-electronic-reporting.md#Configuration) da [biblioteca de ativos compartilhados](../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> O uso do LCS como repositório de armazenamento para configurações de ER está sendo [preterido](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Para mais informações, consulte [Regulatory Configuration Service (RCS) - Suspensão do armazenamento do Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).

1. Entre no aplicativo usando uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

2. Acesse **Administração da organização** &gt; **Espaços de trabalho** &gt; **Relatório eletrônico**.
3. Na seção **Provedores de configuração**, selecione o bloco **Microsoft**.
4. No bloco **Microsoft**, selecione **Repositórios**.

    [![Bloco da Microsoft na página Configurações de localização.](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. Na página **Repositórios de configuração**, na grade, selecione o repositório existente do tipo **LCS**. Se esse repositório não aparecer na grade, siga estas etapas:

    1. Selecione **Adicionar** para adicionar um repositório.
    2. Selecione **LCS** como tipo de repositório.
    3. Selecione **Criar repositório**.
    4. Se você for solicitado sobre autorização, siga as instruções na tela.
    5. Insira um nome e uma descrição para o repositório.
    6. Selecione **OK** para confirmar a nova entrada do repositório.
    7. Na grade, selecione o novo repositório do tipo **LCS**.

6. Selecione **Abrir** para exibir a lista de configurações de ER para o repositório selecionado.

    [![Página Repositórios de configuração.](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Se você tiver problemas ao acessar o repositório LCS para baixar configurações da biblioteca de ativos compartilhados no LCS, poderá baixar configurações do [Repositório global](er-download-configurations-global-repo.md).

7. Na árvore de configurações, no painel esquerdo, selecione a configuração ER necessária.
8. Na Guia Rápida **Versões**, selecione a versão necessária da configuração de ER selecionada.
9. Selecione **Importar** para baixar a versão selecionada do LCS para a instância atual.

    > [!NOTE]
    > O botão **Importar** não está disponível para as versões de configuração do ER que já estão presentes na instância atual.

    [![Página do repositório de configuração.](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> Dependendo das configurações de ER, as configurações são validadas depois que são importadas. Talvez você seja notificado sobre problemas de inconsistências descobertos. Você deve resolver esses problemas para que possa usar a versão de configuração importada. Para obter mais informações, consulte a lista de artigos relacionados deste artigo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório Eletrônico (ER)](general-electronic-reporting.md)

[Baixar configurações ER do repositório global de serviço de configuração](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
