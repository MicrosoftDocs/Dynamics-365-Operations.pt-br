---
title: "Espaço de trabalho móvel de entrada de tempo do projeto para o aplicativo Dynamics 365 for Operations"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel de entrada de tempo do projeto. Este espaço de trabalho permite que os usuários insiram e economizem tempo com um projeto usando seu dispositivo móvel."
author: annbe
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9c592c301908898915164e9236850759b73543fe
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Espaço de trabalho móvel de entrada de tempo do projeto

[!include[banner](../includes/banner.md)]



Este tópico fornece informações sobre o espaço de trabalho móvel de entrada de tempo do projeto para o aplicativo móvel Dynamics 365 for Operations. Este espaço de trabalho permite que os usuários insiram e economizem tempo com um projeto usando seu dispositivo móvel.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>Visão geral do espaço de trabalho móvel de entrada de tempo do projeto
---------------------------------------------------

Como parte do trabalho diário, os recursos de projetos são frequentemente no local ou em trânsito. O espaço de trabalho móvel **Entrada de tempo de projeto** permite que os usuários insiram tempo faturável ou não faturável em um projeto no dispositivo móvel de sua escolha. Portanto, recursos do projeto podem gravar entradas de tempo a qualquer momento e em qualquer lugar. Também podem exibir as entradas de horas que já foram registradas. 

Especificamente, o espaço de trabalho móvel **Entrada de tempo de projeto** fornece estes recursos:

-   Para qualquer data selecionada, insira o número de horas que passou de uma tarefa específica.
-   Pesquisar o nome do projeto ou cliente para localizar o projeto para inserir tempo.
-   Especifique a categoria e a atividade do tempo que passou.
-   Registre o tempo como faturável ou não faturável para o projeto.
-   Opcionalmente insira comentários internos ou externos.

Para implementar o espaço de trabalho móvel **Entrada de tempo do projeto** consulte as seguintes seções deste tópico.

## <a name="prerequisites"></a>Pré-requisitos
Antes de implementar o espaço de trabalho móvel **Entrada de tempo do projeto**, certifique-se de que seu administrador do sistema preencheu os seguintes pré-requisitos.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Função</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Deve ser implementada a versão 1611 com atualização 3 ou superior de plataforma do Microsoft Dynamics 365.</td>
<td>Administrador do sistema</td>
<td>Se ainda não tiver o Dynamics 365 for Operations implantado em sua organização, o administrador do sistema deverá ver <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implantar o ambiente de demonstração do Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>O KB 4018050 deve ser implementado.</td>
<td>Administrador do sistema</td>
<td>o KB 4018050 é um hotfix de metadados ou atualização X++ que contém o espaço de trabalho móvel <strong>Entrada de tempo do projeto</strong>. Para implementar o KB 4018050, o administrador do sistema deve seguir estas etapas.
<ol>
<li>Baixe o KB 4018050 do Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar o hotfix de metadados</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Crie um pacote implantável</a> que contenha os modelos <strong>ApplicationSuite</strong> e <strong>ProjectMobile</strong> e, em seguida, carregue o pacote implantável para o LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplique o pacote implantável</a> ao seu sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>O espaço de trabalho <strong>Entrada de tempo do projeto</strong> deve ser publicado para o aplicativo móvel Dynamics 365 for Operations.</td>
<td>Administrador do sistema</td>
<td><ol>
<li>Inicie o Dynamics 365 for Operations em seu navegador.</li>
<li>Na página <strong>Parâmetros do sistema</strong>, na guia <strong>Gerenciar espaços de trabalho móveis</strong>, selecione o espaço de trabalho <strong>Entrada de tempo do projeto</strong>.</li>
<li>Clique em <strong>Publicar espaço de trabalho móvel</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Baixe e instale o aplicativo móvel Dynamics 365 for Operations
Baixe e instale o aplicativo móvel Dynamics 365 for Operations de sua loja de aplicativos móveis.

-   Para Android: [Dynamics 365 for Operations na Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Dynamics 365 for Operations na iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Entre no aplicativo móvel Dynamics 365 for Operations
1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira a URL do Dynamics 365 for Operations.
3.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
4.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Dynamics 365 for Operations. Insira suas credenciais.
5.  Após se conectar, você verá os espaços de trabalho da sua empresa. Observe que se o seu administrador de sistema publicar uma nova área de trabalho depois, você pode efetuar pull para atualizar a lista dos espaços de trabalho móveis.

[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Insira o tempo usando o espaço de trabalho móvel Entrada de tempo do projeto
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Entrada de tempo do projeto**.
2.  Selecione **Entrada de tempo**. Você verá as datas de calendário da semana atual.
3.  Para uma data selecionada, selecione **Ações** &gt; **Nova entrada**.
4.  Insira o número de horas a serem registradas.
5.  Selecionar o projeto para a entrada de hora. Você verá uma lista de projetos que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem ver [plataforma móvel do Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Se seu projeto não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquisar por nome ou alternar para pesquisar por nome do projeto ou cliente.
7.  Selecione uma categoria. Você verá uma lista de categorias que estão carregadas para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem ver [plataforma móvel do Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Se sua categoria não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquise por categoria ou alterne para pesquisar por nome de categoria.
9.  Selecione uma atividade. Você verá uma lista de atividades que estão carregadas para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem ver [plataforma móvel do Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Se sua atividade não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquise por número de atividade ou alterne para pesquisar por finalidade.
11. Selecionar a propriedade da linha.
12. Opcional: insira comentários internos ou externos.
13. Selecione **Concluído**.






