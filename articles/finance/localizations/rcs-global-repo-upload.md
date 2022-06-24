---
title: Criar configurações de ER no RCS e carregá-las no Repositório global
description: Este artigo explica como criar a configuração de relatório eletrônico (ER) no Microsoft Regulatory Configuration Services e carregá-lo para o Repositório global.
author: JaneA07
ms.date: 01/11/2021
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
ms.openlocfilehash: 8cfbcfea3c6056d87eb600c9a2f9e0d1727c30ff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894733"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Criar configurações de ER no Regulatory Configuration Services (RCS) e carregá-las no Repositório global

[!include [banner](../includes/banner.md)]

Você pode usar o Microsoft Regulatory Configuration Services (RCS) para criar configurações de relatório eletrônico (ER) e publicá-los para que possam ser usados em sua organização.

Os procedimentos a seguir explicam como um usuário na função de administrador do sistema ou de relatório eletrônico pode criar uma versão derivada da configuração ER que foi configurada em uma instância RCS e, em seguida, carregar a configuração derivada para o repositório global. 

Antes de concluir esses procedimentos, conclua os seguintes pré-requisitos:

- Ter acesso a um ambiente RCS para sua organização.
- Criar um provedor de configuração ativo e torná-lo ativo. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Você deve verificar se um ambiente RCS foi provisionado para sua organização. Se você não tiver uma instância RCS configurada para sua organização, poderá fazer isso usando as seguintes etapas:

1. Em um aplicativo Finance and Operations, vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Em **Links relacionados/Links externos**, selecione **Regulatory services – Configuração** e siga as instruções para **Entrar** para provisionar um.

Se um ambiente RCS já foi provisionado para sua organização, use a URL da página para acessá-lo e selecione a opção **Entrar**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Criar uma versão derivada de uma configuração no RCS

> [!NOTE]
> Se estiver usando o RCS pela primeira vez, não terá configuração disponível da qual derivar. Será necessário importar uma configuração do Repositório global. Para obter mais informações, consulte [Baixar configurações ER do repositório global de serviço de configuração](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Entre** no RCS e selecione o espaço de trabalho **Relatório eletrônico**.
2. Verifique se você tem um provedor de configuração ativo para sua organização que esteja definido como ativo (ver pré-requisitos). 
3. Selecione **Configurações de relatórios**.
4. Selecione a configuração da qual você deseja derivar uma nova versão. Você pode usar o campo de filtro acima da árvore para restringir a pesquisa.
5. Selecione **Criar configuração** \> **Derivar de Nome**.
6. Insira um nome e uma descrição e, depois, selecione **Criar configuração** para criar uma nova versão derivada com o status 'Rascunho'.
7. Selecione a nova configuração derivada e faça alterações adicionais no formato de configuração, se necessário. 
8. Depois que as alterações forem concluídas, você precisará definir **Alterar status** para a configuração como **Concluído** para poder publicá-la no repositório. Selecione **OK**.

![Nova versão de configuração no RCS.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Quando o status da configuração for alterado, você poderá receber uma mensagem de erro de validação relacionada aos aplicativos conectados. Para desativar a validação, no Painel de Ações, na guia **Configurações**, selecione **Parâmetros do usuário** e defina a opção **Ignorar validação na alteração e troca do status de configuração** para **Sim** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Carregar uma configuração para o Repositório global

Para compartilhar uma configuração nova ou derivada com sua organização, você pode carregá-la no Repositório global seguindo estas etapas:

1. Selecione a versão concluída da configuração e, em seguida, selecione **Carregar no repositório**.
2. Selecione a opção **Global (Microsoft)** e, em seguida, selecione **Carregar**.

    ![Carregar em opções de repositório.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Na caixa de mensagem de confirmação, selecione **Sim**. 
4. Atualize a descrição da versão conforme necessário e, em seguida, selecione **OK**. Outra opção é carregar a versão em um aplicativo conectado ou em um repositório do GIT.  

O status da configuração é atualizado para **Compartilhado** e a configuração é carregada no Repositório global. Uma versão de rascunho da configuração carregada também é criada e poderá ser usada se forem necessárias alterações subsequentes.

Depois que a configuração for carregada no Repositório global, você poderá trabalhar com ela, das seguintes maneiras:

- Importe-o para a instância do Dynamics 365. Para obter mais informações, consulte [Importar configurações do ER a partir de RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Compartilhar com terceiros ou com uma organização externa, consulte [Configurações de relatório eletrônico de compartilhamento RCS (ER) com organizações externas](rcs-global-repo-share-configuration.md)

    ![Versão de configuração da Contoso do Intrastat derivada no Repositório global.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Excluir uma configuração do Repositório global
Conclua as etapas a seguir para excluir uma configuração criada pela sua organização.

1. No espaço de trabalho **Relatório eletrônico**, verifique se seu provedor de configuração está **Ativo**. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. No provedor de configuração ativo, selecione **repositório**.
3. Selecione o tipo de repositório **Global** e selecione **Abrir**.
4. Na Guia Rápida **Filtro**, localize a configuração que deseja excluir usando a funcionalidade de **Filtro**.
5. Na Guia Rápida **Versão**, selecione a versão da configuração que deseja excluir e, em seguida, selecione **Excluir**:

    ![Excluir configuração do repositório global.](media/RCS_Delete_from_GlobalRepo.JPG)

6. Na caixa de mensagem de confirmação, selecione **Sim**.

    ![Excluir mensagem de confirmação de versão de configuração.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
A versão de configuração é excluída e a mensagem de confirmação é exibida. 

> [!NOTE]
> As configurações só podem ser excluídas pelo provedor de configuração que as criou. Se a configuração tiver sido compartilhada com outra organização, terá de ser descompartilhada antes de ser excluída.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
