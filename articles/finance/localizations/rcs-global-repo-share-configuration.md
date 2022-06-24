---
title: Compartilhar configurações de ER no RCS/Repositório global com organizações externas
description: Este artigo explica como compartilhar as configurações de relatório eletrônico (ER) no Microsoft Regulatory Configuration Services/o Repositório global diretamente com organizações externas.
author: JaneA07
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 976a86aee75581d1afa764bea049b6c0eaecf9f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888913"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>Compartilhar as configurações de relatório eletrônico (ER) no Regulatory Configuration Services/Repositório global diretamente com organizações externas

[!include [banner](../includes/banner.md)]

Você pode usar o Microsoft Regulatory Configuration Services (RCS) para compartilhar configurações de relatório eletrônico (ER) e publicá-los em organizações externas.

Os procedimentos a seguir explicam como um usuário RCS pode compartilhar uma versão de uma configuração ER que foi configurada em uma instância RCS com uma organização externa. Antes de concluir esses procedimentos, conclua os seguintes pré-requisitos:

- Acessar uma instância RCS.
- Criar um fornecedor de configuração ativa. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
- Criar e carregar uma nova versão de uma configuração ER. Para obter mais informações, consulte [Criar e carregar uma nova versão de uma configuração de relatório eletrônico (ER)](rcs-global-repo-upload.md).

Você também deve verificar se um ambiente RCS foi provisionado para sua empresa.

1. Em um aplicativo Finance and Operations, vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Se não tiver o ambiente do RCS provisionado para sua empresa, clique no link externo **Regulatory services – Configuração** e siga as instruções para provisionar um.

Se um ambiente RCS já foi provisionado para sua empresa, use a URL da página para acessá-lo, selecionando a opção de entrada.

## <a name="verify-the-configuration-that-you-want-to-share"></a>Verificar a configuração que você deseja compartilhar

Siga estas etapas para verificar se a configuração que você deseja compartilhar já foi carregada no repositório global.

1. No espaço de trabalho **Relatório eletrônico**, selecione **Repositórios** para o provedor de configuração.

    ![Provedores de configuração.](media/1_RCS_Repo_for_config_provider.JPG)

2. Selecione **Repositório global** \> **Abrir**.
3. Pesquise pela configuração que você deseja compartilhar. Você pode usar o campo de filtro para restringir a pesquisa. Se você não conseguir localizar a configuração no repositório global, siga as etapas em [Criar e carregar uma nova versão de uma configuração de relatório eletrônico (ER)](rcs-global-repo-upload.md).

## <a name="share-er-configurations-with-external-organizations"></a>Compartilhar configurações de ER com organizações externas

Depois que uma configuração é criada no provedor de configuração, você pode compartilhá-la diretamente com as organizações externas usando a Guia Rápida **Compartilhado com** na página **Repositório de configuração global**.

1. No espaço de trabalho **Relatório eletrônico**, selecione **Repositórios** para o provedor de configuração.
2. Selecione **Repositório global** \> **Abrir**. 
3. Selecionar a configuração que você deseja compartilhar.
4. Na Guia Rápida **Compartilhado com**, selecione **Organização**.

    ![Compartilhado com Guia Rápida.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. Na caixa de diálogo, insira o nome do domínio para a organização externa e selecione **OK**.

    ![Compartilhar versão de configuração com caixa de diálogo de organização externa.](media/1_RCS_Repo_for_Share_with_form.JPG)

A configuração é compartilhada com a organização externa e está disponível para aquela organização no repositório global. A partir daí, ele pode ser importado para a instância da organização do RCS ou para suas instâncias de aplicativos de finanças e operações.

6. Para cancelar o compartilhamento uma configuração que já tenha sido compartilhada com uma organização externa, selecione a configuração e clique em **Cancelar compartilhamento** e selecione **OK**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]