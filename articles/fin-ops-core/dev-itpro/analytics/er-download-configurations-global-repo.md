---
title: Baixar configurações ER do repositório global de serviço de configuração
description: Este artigo explica como baixar as configurações de relatório eletrônico (ER) do repositório global do serviço de configuração.
author: kfend
ms.date: 06/02/2020
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
ms.openlocfilehash: 3bbc341d1668e54fcb4034263a7e142166a94b05
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273298"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>Baixar configurações ER do repositório global de serviço de configuração

[!include [banner](../includes/banner.md)]

Este artigo explica como baixar as [configurações de relatório eletrônico (ER)](general-electronic-reporting.md#Configuration) do repositório global do serviço de configuração. Para obter mais informações, consulte [Microsoft Dynamics 365 Finance - Regulatory services, serviço de configuração](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Abra o repositório de configurações

1. Entre no aplicativo Dynamics 365 Finance usando uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

2. Vá par **Administração da organização > Espaços de trabalho > Relatório eletrônico**.
3. Na seção **Provedores de configuração**, selecione o bloco **Microsoft**.
3. No bloco **Microsoft**, selecione **Repositórios**.

    ![Espaço de trabalho de relatório eletrônico.](./media/er-download-configurations-global-repo-er-workspace.png)

4. Na página **Repositórios de configuração**, na grade, selecione o repositório existente do tipo **Global**. Se esse repositório não aparecer na grade, siga estas etapas:

    1. Selecione **Adicionar** para adicionar um novo repositório.
    2. Selecione **Global** como o tipo de repositório e, em seguida, selecione **Criar repositório**.
    3. Se solicitado, siga as instruções de autorização.
    4. Insira um nome e uma descrição para o repositório e, em seguida, selecione **OK** para confirmar a nova entrada de repositório.
    5. Na grade, selecione o novo repositório do tipo **Global**.

5. Selecione **Abrir** para exibir a lista de configurações de ER para o repositório selecionado.

    ![Página Repositórios de configuração.](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Importar uma única configuração

1. Na página **Repositórios de configuração**, na árvore de configurações, selecione a configuração ER desejada.
2. Na Guia Rápida **Versões**, selecione a versão necessária da configuração de ER selecionada.
3. Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.

    > [!NOTE]
    > O botão **Importar** não está disponível para as versões de configuração do ER que já estão presentes na instância atual do Finance.

    ![Página Repositório de configuração, FastTab Configurações.](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Importar configurações filtradas

1. Na página **Repositórios de configuração**, na árvore configurações, expanda a FastTab **Filtro**.
2. Na grade **Marcas**, adicione as marcas necessárias.
3. No campo **Aplicabilidade de país/região**, selecione os códigos de país/região adequados e selecione **Aplicar filtro**.

    > [!NOTE]
    > A FastTab **Configurações** mostra todas as configurações que atendem às condições de seleção especificadas.

4. Na FastTab **Configurações**, selecione **Importar** para baixar as configurações filtradas do repositório global para a instância atual.
5. Na guia **Configurações**, selecione **Redefinir filtro** para limpar as condições de seleção especificadas.

    ![Página Repositório de configuração, FastTab Versões, botão Importar.](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> Dependendo das configurações de ER, as configurações são validadas depois que são importadas. Talvez você seja notificado sobre problemas de inconsistências descobertos. Antes de poder usar a versão de configuração importada, você precisa resolver os problemas. Para obter mais informações, consulte a lista de recursos relacionados deste artigo.

> [!NOTE]
> As configurações de ER podem ser definidas como dependentes de outras configurações. Portanto, juntamente com uma configuração selecionada, outras configurações podem ser importadas automaticamente. Para saber mais sobre dependências de configuração, consulte [Definir a dependência de configurações do ER em outros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

