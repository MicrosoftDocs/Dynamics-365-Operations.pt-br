---
title: "Espaço de trabalho móvel de entrada de tempo do projeto"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel de entrada de tempo do projeto. Este espaço de trabalho permite que os usuários insiram e economizem tempo com um projeto usando seu dispositivo móvel."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9bf79af6eea6f899158fc3c8d523587cb11c90ad
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="project-time-entry-mobile-workspace"></a>Espaço de trabalho móvel de entrada de tempo do projeto

[!include[banner](../includes/banner.md)]

Este tópico fornece informações sobre a área de trabalho móvel de **Entrada de tempo do projeto**. Este espaço de trabalho permite que os usuários insiram e economizem tempo com um projeto usando seu dispositivo móvel.

O espaço de trabalho móvel é destinado a ser usado com o Microsoft Dynamics 365 do aplicativo móvel Operações Unificadas. 

## <a name="overview"></a>Visão Geral
Como parte do trabalho diário, os recursos de projetos são frequentemente no local ou em trânsito. O espaço de trabalho móvel **Entrada de tempo de projeto** permite que os usuários insiram tempo faturável ou não faturável em um projeto no dispositivo móvel de sua escolha. Portanto, recursos do projeto podem gravar entradas de tempo a qualquer momento e em qualquer lugar. Também podem exibir as entradas de horas que já foram registradas. 

Especificamente, na área de trabalho móvel **Entrada de tempo do projeto**, os usuários podem executar estas tarefas:

-   Para qualquer data selecionada, insira o número de horas que passou de uma tarefa específica.
-   Pesquisar o nome do projeto ou cliente para localizar o projeto para inserir tempo.
-   Especifique a categoria e a atividade do tempo que passou.
-   Registre o tempo como faturável ou não faturável para o projeto.
-   Opcionalmente insira comentários internos ou externos.

## <a name="prerequisites"></a>Pré-requisitos
Os pré-requisitos diferem, com base da versão do Microsoft Dynamics 365 que foi implantada para sua organização.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Pré-requisitos se você usa o Microsoft Dynamics 365 for Finance and Operations
Se o Microsoft Dynamics 365 for Finance and Operations foi implantado em sua organização, o administrador do sistema deve publicar o espaço de trabalho móvel **Entrada de hora de projeto**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Pré-requisitos se você usar o Microsoft Dynamics 365 for Operations versão 1611 com a atualização da plataforma 3 ou posterior
Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização da plataforma 3 ou posterior tiver sido implantado em sua organização, o administrador do sistema deve completar os seguintes pré-requisitos. 

<table>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Função</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td>Implementar o KB 4018050.</td>
<td>Administrador do sistema</td>
<td>o KB 4018050 é um hotfix de metadados ou atualização X++ que contém o espaço de trabalho móvel <strong>Entrada de tempo do projeto</strong>. Para implementar o KB 4018050, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crie um pacote implantável</a> que contenha os modelos <strong>ApplicationSuite</strong> e <strong>ProjectMobile</strong> e, em seguida, carregue o pacote implantável para o LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publique a área de trabalho móvel <strong>Entrada de tempo do projeto</strong>.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.

Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:

-   [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel
1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira sua URL do Dynamics 365.
3.  Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.
4.  Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Insira o tempo usando o espaço de trabalho móvel Entrada de tempo do projeto
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Entrada de tempo do projeto**.
2.  Selecione **Entrada de tempo**. Você verá as datas de calendário da semana atual.
3.  Para uma data selecionada, selecione **Ações** &gt; **Nova entrada**.
4.  Insira o número de horas a serem registradas.
5.  Selecionar o projeto para a entrada de hora. Você verá uma lista de projetos que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, consulte a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
6.  Se o projeto não estiver na lista, selecione **Pesquisar**. Pesquisar por nome ou alternar para pesquisar por nome do projeto ou cliente.
7.  Selecione uma categoria. Você verá uma lista de categorias que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, consulte a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
8.  Se a categoria não estiver na lista, selecione **Pesquisar**. Pesquise por categoria ou alterne para pesquisar por nome de categoria.
9.  Selecione uma atividade. Você verá uma lista de atividades que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, consulte a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
10. Se a atividade não estiver na lista, selecione **Pesquisar**. Pesquise por número de atividade ou alterne para pesquisar por finalidade.

11. Selecionar a propriedade da linha.
12. Opcional: insira comentários internos ou externos.
13. Selecione **Concluído**.

