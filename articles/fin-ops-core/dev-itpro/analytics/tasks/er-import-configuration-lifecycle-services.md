---
title: Importar uma configuração do Lifecycle Services
description: Este tópico explica como um usuário na função de Administrador do sistema ou Desenvolvedor de relatório eletrônico pode importar uma nova versão de uma configuração do Relatório eletrônico (RE) do Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c43cdce8d073f04a3158c8beb13a5376e669a4c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684442"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Importar uma configuração do Lifecycle Services

[!include [banner](../../includes/banner.md)]

Este tópico explica como um usuário na função de Administrador do sistema ou Desenvolvedor de relatório eletrônico pode importar uma nova versão de uma [configuração do Relatório eletrônico (ER)](../general-electronic-reporting.md#Configuration) a partir da [biblioteca Ativo em nível de projeto](../../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).

Neste exemplo, você selecionará a versão desejada da configuração de ER e a importará para uma empresa de exemplo chamada Litware, Inc. Essas etapas podem ser concluídas em qualquer empresa, pois as configurações ER são compartilhadas entre as empresas. Para completar essas etapas, você deve primeiro completar as etapas em [Carregar uma configuração ER no Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). O acesso ao LCS também é necessário.

1. Entre no aplicativo usando uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Administrador do sistema

2. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. Selecione **Configurações**.

<a name="accessconditions"></a>
> [!NOTE]
> Verifique se o usuário atual do Dynamics 365 Finance é membro do projeto LCS que contém a biblioteca de ativos que o usuário deseja [acessar](../../lifecycle-services/asset-library.md#asset-library-support) para importar configurações ER.
>
> Não é possível acessar um projeto LCS a partir de um repositório ER que representa um domínio diferente daquele usado no Finance. Se você tentar, uma lista vazia de projetos LCS será mostrada e não será possível importar configurações ER da biblioteca de ativos em nível de projeto no LCS. Para acessar as bibliotecas de ativos em nível de projeto a partir de um repositório ER usado para importar configurações ER, entre no Finance usando as credenciais de um usuário que pertença ao locatário (domínio) para o qual a instância do Finance atual foi provisionada.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Excluir uma versão compartilhada de uma configuração do modelo de dados

1. Na página **Configurações**, na árvore de configurações, selecione **Configuração do modelo de exemplo**.

    Você criou a primeira versão de uma configuração do modelo de dados de exemplo e publicou-a no LCS ao concluir as etapas em [Carregar uma configuração no Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). Nesse procedimento, você excluirá esta versão da configuração ER. Você importará essa versão do LCS mais adiante neste tópico.

2. Na lista, localize e selecione o registro desejado.

    Neste exemplo, selecione a versão da configuração com status **Compartilhado**. Este status indica que a configuração esteve publicada ao LCS.

3. Selecione **Alterar status**.
4. Selecione **Descontinuar**.

    Ao alterar o status da versão selecionada de **Compartilhado** para **Descontinuado**, você disponibiliza a versão para exclusão.

5. Selecione **OK**.
6. Na lista, localize e selecione o registro desejado.

    Neste exemplo, selecione a versão da configuração com status **Descontinuado**.

7. Selecione **Excluir**.
8. Selecione **Sim**.

    Observe que somente a versão de rascunho 2 da configuração do modelo de dados selecionado está disponível agora.

9. Feche a página.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Importar uma versão compartilhada de uma configuração do modelo de dados do LCS

1. Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.

2. Na seção **Provedores de configuração**, selecione o bloco **Litware, Inc.**.

3. No bloco **Litware, Inc.**, selecione **Repositórios**.

    Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.

4. Selecione **Abrir**.

    Para este exemplo, selecione o repositório **LCS** e abra-o. Você deve ter [acesso](#accessconditions) ao projeto LCS e à biblioteca de ativos que é acessada pelo repositório ER selecionado.

5. Na lista, marque a linha selecionada.

    Para este exemplo, selecione a primeira versão da **Configuração de modelo de exemplo** na lista de versões.

6. Selecione **Importar**.
7. Selecione **Sim** para confirmar a importação da versão selecionada de LCS.

    Uma mensagem informativa confirma que a versão selecionada foi importada com êxito.

8. Feche a página.
9. Feche a página.
10. Selecione **Configurações**.
11. Na árvore, selecione **Configuração do modelo de exemplo**.
12. Na lista, localize e selecione o registro desejado.

    Neste exemplo, selecione a versão da configuração com status **Compartilhado**.

    Observe que versão 1 compartilhada da configuração do modelo de dados selecionado agora também está disponível.
