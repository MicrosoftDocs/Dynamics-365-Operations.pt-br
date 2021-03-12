---
title: Criar configurações de ER no RCS e carregá-las no Repositório global
description: Este tópico explica como criar a configuração de relatório eletrônico (ER) no Microsoft Regulatory Configuration Services e carregá-lo para o Repositório global.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: ef12c911c8953b181db1c0eff0874a3d8cfcb3da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005739"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Criar configurações de ER no Regulatory Configuration Services (RCS) e carregá-las no Repositório global

[!include [banner](../includes/banner.md)]

Você pode usar o Microsoft Regulatory Configuration Services (RCS) para criar configurações de relatório eletrônico (ER) e publicá-los para que possam ser usados em sua organização.

Os procedimentos a seguir explicam como um usuário na função de administrador do sistema ou de relatório eletrônico pode criar uma versão derivada da configuração ER que foi configurada em uma instância RCS e, em seguida, carregar a configuração derivada para o repositório global. 

Antes de concluir esses procedimentos, conclua os seguintes pré-requisitos:

- Acessar uma instância RCS.
- Criar um fornecedor de configuração ativa. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Você também deve verificar se um ambiente RCS foi provisionado para sua empresa.

1. Em um aplicativo do Finance and Operations, acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Se não tiver o ambiente do RCS provisionado para sua empresa, clique no link externo **Regulatory services – Configuração** e siga as instruções para provisionar um.

Se um ambiente RCS já foi provisionado para sua empresa, use a URL da página para acessá-lo, selecionando a opção de entrada.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Criar uma versão derivada de uma configuração no RCS

1. No espaço de trabalho **Relatório eletrônico**, verifique se você tem um provedor de configuração ativo para sua organização. 
2. Selecione **Configurações de relatórios**.
3. Selecione a configuração da qual você deseja derivar uma nova versão. Você pode usar o campo de filtro acima da árvore para restringir a pesquisa.
4. Selecione **Criar configuração** \> **Derivar de Nome**.
5. Insira um nome e uma descrição e selecione **Criar configuração** para criar uma nova versão derivada.
6. Selecione a configuração derivada recentemente, adicione uma descrição da versão e, em seguida, selecione **OK**. O status da configuração a é alterado para **Concluído**.

![Nova versão de configuração no RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Quando o status da configuração for alterado, você poderá receber uma mensagem de erro de validação relacionada aos aplicativos conectados. Para desativar a validação, no Painel de Ações, na guia **Configurações**, selecione **Parâmetros do usuário** e defina a opção **Ignorar validação na alteração e troca do status de configuração** para **Sim** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Carregar uma configuração para o Repositório global

Para compartilhar uma configuração nova ou derivada com sua organização, você pode carregá-la no Repositório global.

1. Selecione a versão concluída da configuração e, em seguida, selecione **Carregar no repositório**.
2. Selecione a opção **Global (Microsoft)** e, em seguida, selecione **Carregar**.

    ![Carregar em opções de repositório](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Na caixa de mensagem de confirmação, selecione **Sim**. 
4. Atualize a descrição da versão conforme necessário e, em seguida, selecione **OK**. 

O status da configuração é atualizado para **Compartilhar** e a configuração é carregada no repositório global. A partir daí, você pode trabalhar com ela da seguinte maneira:

- Importe-o para a instância do Dynamics 365. Para obter mais informações, consulte [Importar configurações do ER a partir de RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Compartilhar com terceiros ou com uma organização externa, consulte [Configurações de relatório eletrônico de compartilhamento RCS (ER) com organizações externas](rcs-global-repo-share-configuration.md)

    ![Versão de configuração da Contoso do Intrastat derivada no Repositório global](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Excluir uma configuração do Repositório global
Conclua as etapas a seguir para excluir uma configuração criada pela sua organização.

1. No espaço de trabalho **Relatório eletrônico**, verifique se seu provedor de configuração está **Ativo**. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. No provedor de configuração ativo, selecione **repositório**.
3. Selecione o tipo de repositório **Global** e selecione **Abrir**.
4. Na Guia Rápida **Filtro**, localize a configuração que deseja excluir usando a funcionalidade de **Filtro**.
5. Na Guia Rápida **Versão**, selecione a versão da configuração que deseja excluir e, em seguida, selecione **Excluir**:

    ![Excluir configuração do repositório global](media/RCS_Delete_from_GlobalRepo.JPG)

6. Na caixa de mensagem de confirmação, selecione **Sim**.

    ![Excluir mensagem de confirmação de versão de configuração](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
A versão de configuração é excluída e a mensagem de confirmação é exibida. 

> [!NOTE]
> As configurações só podem ser excluídas pelo provedor de configuração que as criou. Se a configuração tiver sido compartilhada com outra organização, terá de ser descompartilhada antes de ser excluída.
 
