---
title: Carregar uma configuração no Lifecycle Services
description: Este tópico explica como criar uma nova configuração de relatório eletrônico (ER) e carregá-la no Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92fc6d7a8b2508c9a1f7b56ca8115adbd6ae00ea
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092532"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Carregar uma configuração no Lifecycle Services

[!include [banner](../../includes/banner.md)]

Este tópico explica como um usuário na função de Administrador do sistema ou Desenvolvedor de relatório eletrônico pode criar uma nova [configuração do Relatório eletrônico (ER)](../general-electronic-reporting.md#Configuration) e carregá-la na [biblioteca Ativo em nível de projeto](../../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).

Neste exemplo, você criará uma configuração e a carregará no LCS para uma empresa de exemplo chamada Litware, Inc. Estas etapas podem ser concluídas em qualquer empresa, pois as configurações ER são compartilhadas entre todas as empresas. Para concluir estas etapas, primeiro conclua as etapas em [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). O acesso ao LCS também é necessário.

1. Entre no aplicativo usando uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Administrador do sistema

2. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. Selecione **Litware, Inc.** e marque-a como **Ativa**.
4. Selecione **Configurações**.

<a name="accessconditions"></a>
> [!NOTE]
> Verifique se o usuário atual do Dynamics 365 Finance é membro do projeto LCS que contém a [biblioteca de ativos](../../lifecycle-services/asset-library.md#asset-library-support) que é usada para importar configurações ER.
>
> Não é possível acessar um projeto LCS a partir de um repositório ER que representa um domínio diferente daquele usado no Finance. Se você tentar, uma lista vazia de projetos LCS será mostrada e não será possível importar configurações ER da biblioteca de ativos em nível de projeto no LCS. Para acessar as bibliotecas de ativos em nível de projeto a partir de um repositório ER usado para importar configurações ER, entre no Finance usando as credenciais de um usuário que pertença ao locatário (domínio) para o qual a instância do Finance atual foi provisionada.

## <a name="create-a-new-data-model-configuration"></a>Criar uma nova configuração de modelo de dados

1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, selecione **Criar configuração** para abrir a caixa de diálogo suspensa.

    Neste exemplo, você criará uma configuração contendo um modelo de dados de exemplo para documentos eletrônicos. Esta configuração do modelo de dados será carregada no LCS posteriormente.

3. No campo **Nome**, insira **Configuração do modelo de exemplo**.
4. No campo **Descrição**, insira **Configuração do modelo de exemplo**.
5. Selecione **Criar configuração**.
6. Selecione **Designer de modelos**.
7. Selecione **Novo**.
8. No campo **Nome**, insira **Ponto de entrada**.
9. Selecione **Adicionar**.
10. Selecione **Salvar**.
11. Feche a página.
12. Selecione **Alterar status**.
13. Selecione **Concluir**.
14. Selecione **OK**.
15. Feche a página.

## <a name="register-a-new-repository"></a>Registrar um novo repositório

1. Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.

2. Na seção **Provedores de configuração**, selecione o bloco **Litware, Inc.**.

3. No bloco **Litware, Inc.**, selecione **Repositórios**.

    Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.

4. Selecione **Adicionar** para abrir a caixa de diálogo suspensa.

    Agora você pode adicionar um novo repositório.

5. No campo **Tipo de repositório de configuração**, selecione **LCS**.
6. Selecione **Criar repositório**.
7. No campo **Projeto**, insira ou selecione um valor.

    Para este exemplo, selecione o projeto LCS desejado. Você deve ter [acesso](#accessconditions) ao projeto.

8. Selecione **OK**.

    Concluir uma nova entrada de armazenamento.

9. Na lista, marque a linha selecionada.

    Para este exemplo, selecione o registro de repositório **LCS**.

    Observe que um repositório registrado é marcado pelo provedor atual. Em outras palavras, somente as configurações pertencentes a esse provedor podem ser colocadas neste repositório e, portanto, carregadas no projeto LCS selecionado.

10. Selecione **Abrir**.

    Você abre o repositório para exibir a lista de configurações ER. Se o projeto selecionado ainda não tiver sido usado para compartilhamento de configurações ER, a lista estará vazia.

11. Feche a página.
12. Feche a página.

## <a name="upload-a-configuration-into-lcs"></a>Carregar uma configuração no LCS

1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, na árvore de configurações, selecione **Configuração do modelo de exemplo**.

    Selecione uma configuração criada que já esteja concluída.

3. Na lista, localize e selecione o registro desejado.

    Para este exemplo, selecione a versão da configuração selecionada com um status **Concluído**.

4. Selecione **Alterar status**.
5. Selecione **Compartilhar**.

    O status da configuração é alterado de **Concluído** para **Compartilhado** quando a configuração é publicada no LCS.

6. Selecione **OK**.
7. Na lista, localize e selecione o registro desejado.

    Neste exemplo, selecione a versão da configuração com status **Compartilhado**.

    Observe que o status da versão selecionada foi alterado de **Concluído** para **Compartilhado**.

8. Feche a página.
9. Selecione **Repositórios**.

    Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.

10. Selecione **Abrir**.

    Para este exemplo, selecione o repositório **LCS** e abra-o.

    Observe que a configuração selecionada será mostrada como um ativo do projeto do LCS selecionado.

11. Para abrir o LCS, acesse <https://lcs.dynamics.com>.
12. Abra um projeto que foi usado anteriormente para registro do repositório.
13. Abra a biblioteca de ativos do projeto.
14. Selecione o tipo de ativo **Configuração GER**.

    A configuração do ER que você carregou deve ser listada.

    Observe que a configuração do LCS carregado poderá ser importada para outra instância se os provedores tiverem acesso a esse projeto do LCS.
