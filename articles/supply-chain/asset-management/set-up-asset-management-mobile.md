---
title: Configurar o espaço de trabalho móvel Gerenciamento de ativos
description: Este tópico descreve como configurar o Microsoft Dynamics 365 Supply Chain Management e o aplicativo móvel do Finance and Operations (Dynamics 365) para executar um espaço de trabalho móvel Gerenciamento de ativos que os trabalhadores podem usar para realizar tarefas de gerenciamento de ativos.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: bc170df2fc58ae6b42fbc8834caad0bb7cd16f69
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837768"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Configurar o espaço de trabalho móvel Gerenciamento de ativos

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar o Microsoft Dynamics 365 Supply Chain Management e o aplicativo móvel do Finance and Operations (Dynamics 365) para executar um espaço de trabalho móvel **Gerenciamento de ativos** que os trabalhadores podem usar para realizar tarefas de gerenciamento de ativos.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Configurar usuários de funcionários de manutenção no Supply Chain Management

Para cada usuário que precisar de acesso ao espaço de trabalho móvel **Gerenciamento de ativos**, siga estas etapas.

1. No Supply Chain Management, vá para **Recursos humanos \> Trabalhadores** e verifique se há um registro de trabalhador para o usuário que você deseja configurar. Crie um novo registro de trabalhador conforme necessário.
1. Vá para **Gerenciamento de ativos \> Configuração \> Trabalhadores \> Trabalhadores** e verifique se o registro de trabalhador que você identificou (ou criou) na etapa anterior foi mapeado para um registro de funcionário de manutenção. Crie um novo registro de funcionário de manutenção conforme necessário e defina o campo **Trabalhador** como o registro de trabalhador da etapa anterior.
1. Vá para **Gerenciamento de ativos \> Configuração \> Trabalhadores \> Grupos de funcionários de manutenção** e verifique se o registro de funcionário de manutenção que você identificou (ou criou) na etapa anterior pertence a um grupo de funcionários de manutenção.
1. Vá para **Administração do sistema \> Usuários**.
1. Selecione o usuário relevante na grade.
1. Na FastTab **Detalhes do Usuário**, defina o campo **Pessoa** como a conta de trabalhador que você deseja associar à conta de usuário atual. Essa conta de trabalhador deve ser o registro de trabalhador que você identificou (ou criou) na etapa 1 e mapeou para um registro de funcionário de manutenção na etapa 2.

> [!NOTE]
> As permissões de usuário e as funções de segurança se aplicam aos recursos do espaço de trabalho móvel **Gerenciamento de ativos** assim como se aplicam aos recursos da interface de usuário do Supply Chain Management. Portanto, cada usuário configurado para acessar o espaço de trabalho móvel **Gerenciamento de ativos** deve ter as funções de segurança necessárias para executar operações semelhantes diretamente no Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Publicar o espaço de trabalho móvel Gerenciamento de ativos

Para disponibilizar recursos de gerenciamento de ativos no aplicativo móvel do Finance and Operations (Dynamics 365), você deve publicar o espaço de trabalho móvel **Gerenciamento de ativos**.

1. No Supply Chain Management, selecione o botão **Configurações** (o símbolo de engrenagem no canto superior direito) e, em seguida, selecione **Aplicativo móvel** no menu.
1. Na caixa de diálogo **Gerenciar aplicativo móvel**, localize o bloco **Gerenciamento de ativos**. Se ele contiver o texto "Nos metadados - não publicado", o espaço de trabalho ainda não foi publicado. Se ele contiver o texto "Nos metadados - publicado", o espaço de trabalho já foi publicado e você poderá ignorar o restante deste procedimento.

    ![Caixa de diálogo Gerenciar aplicativo móvel](media/mobile-workspaces.png "Caixa de diálogo Gerenciar aplicativo móvel")

1. Selecione o bloco **Gerenciamento de ativos** e, em seguida, selecione **Publicar** na barra de ferramentas. Após alguns segundos, você receberá uma notificação informando que o espaço de trabalho foi publicado com êxito. Além disso, o texto no bloco será alterado para "Nos metadados - publicado".

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Instalar e configurar o aplicativo móvel do Finance and Operations (Dynamics 365)

1. Acesse uma das seguintes lojas de aplicativos para instalar o aplicativo **Microsoft Finance and Operations (Dynamics 365)** no seu dispositivo móvel:

    - [Para dispositivos Google Android](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Para dispositivos Apple iOS](https://go.microsoft.com/fwlink/?linkid=850663)

1. Abra o aplicativo do Finance and Operations (Dynamics 365). A página de entrada será exibida. No campo **Entrar**, insira a URL do Supply Chain Management ou selecione uma URL recente na lista **Ambientes recentes** e, em seguida, toque em **Conectar**.

    ![Página de entrada](media/mobile-app-sign-in.png "Página de entrada")

1. Se for solicitado que você confirme a conexão, marque a caixa de seleção **Estou ciente** e toque em **Conectar**.
1. Na página **Escolher uma conta**, use sua conta Microsoft para entrar no aplicativo móvel.

    A página **Espaços de trabalho** será exibida. Ela lista cada espaço de trabalho móvel que foi publicado pela sua instância do Supply Chain Management.

    ![Lista de espaços de trabalho](media/mobile-app-workspaces.png "Lista de espaços de trabalho")

1. Se for necessário alterar a entidade legal (empresa), toque no botão Menu (às vezes chamado de hambúrguer ou botão de hambúrguer) no canto superior esquerdo e, em seguida, toque em **Alterar empresa**.

    ![Alterar a entidade legal](media/mobile-app-change-comp.png "Alterar a entidade legal")

1. Na página **Espaços de trabalho**, selecione o espaço de trabalho com o qual você deseja trabalhar para abri-lo.

    ![Espaço de trabalho móvel de gerenciamento de ativos](media/mobile-app-asset-workspace.png "Espaço de trabalho móvel de gerenciamento de ativos")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Trabalhar com o espaço de trabalho móvel Gerenciamento de ativos

Para obter mais informações sobre como trabalhar com o espaço de trabalho móvel **Gerenciamento de ativos**, consulte [Usar o espaço de trabalho móvel Gerenciamento de ativos](asset-management-mobile-workspace.md).

Para obter mais informações sobre o aplicativo móvel do Finance and Operations (Dynamics 365), consulte a [Home page do aplicativo móvel](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]