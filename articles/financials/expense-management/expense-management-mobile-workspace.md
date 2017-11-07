---
title: "Espaço de trabalho móvel de gerenciamento de despesas"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel Gerenciamento de despesas. Este espaço de trabalho permite que os usuários capturem e carreguem um recibo, para que possam anexá-lo a um relatório de despesas posteriormente. Os usuários também podem criar rapidamente uma linha de despesa usando um recibo anexado, além de criar e gerenciar seus relatórios de despesas."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7ce4c9d13a8686c82af8acad39d68858e52ba520
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-mobile-workspace"></a>Espaço de trabalho móvel de gerenciamento de despesas

[!include[banner](../includes/banner.md)]

Este tópico fornece informações sobre o espaço de trabalho móvel **Gerenciamento de despesas**. Este espaço de trabalho permite que os usuários capturem e carreguem um recibo, para que possam anexá-lo a um relatório de despesas posteriormente. Os usuários também podem criar rapidamente uma linha de despesa usando um recibo anexado, além de criar e gerenciar seus relatórios de despesas. Adicionalmente, os aprovadores podem usar o espaço de trabalho móvel **Gerenciamento de despesas** para exibir os relatórios de despesas atribuídos a eles, e aprová-los ou rejeitá-los.


O espaço de trabalho móvel é destinado a ser usado com o Microsoft Dynamics 365 do aplicativo móvel Operações Unificadas.


## <a name="overview"></a>Visão Geral

Muitas organizações exigem que uma cópia do recibo seja anexada a um relatório de despesas relacionado a viagem ou a negócios que um funcionário submete para reembolso. O espaço de trabalho móvel **Gerenciamento de despesas** permite que os usuários criem rapidamente novas linhas de despesa no dispositivo móvel de sua preferência usando uma foto do recibo anexada. Como alternativa, os usuários podem tirar uma foto de um recibo e anexá-la a um relatório de despesas depois. Os funcionários também podem criar e gerenciar os relatórios de despesas e então enviá-los para aprovação e reembolso usando seus dispositivos móveis.


Especificamente, o espaço de trabalho móvel **Gerenciamento de despesas** permite que os usuários executem estas tarefas:

- Tirar uma foto de um recibo e carregá-lo no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise. Você poderá anexar essa foto a um relatório de despesas posteriormente.
- Carregar um arquivo como um recibo capturado. Você poderá anexar esse arquivo a um relatório de despesas posteriormente.
- Criar uma nova linha despesa usando um recibo anexado. Você poderá adicionar o item de linha a um relatório de despesas posteriormente, e enviá-lo para aprovação e reembolso.

Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017), você também poderá usar estes recursos:

- Crie um novo relatório de despesas.
- Anexe transações de cartão de crédito e outras despesas anteriormente criadas a um relatório de despesas.
- Crie novas despesas para um relatório de despesas.
- Anexe um recibo de qualquer despesa a um relatório de despesas, tirando uma foto do recibo ou carregando um arquivo como um recibo capturado.
- Dependendo da política de despesas da empresa, adicione a lista de convidados a uma despesa.
- Dependendo da política de despesas da empresa, discrimine as despesas.
- Envie um relatório de despesas para aprovação e reembolso.
- Aprove ou rejeite os relatórios de despesas dos quais você é um aprovador.

## <a name="prerequisites"></a>Pré-requisitos
Os pré-requisitos variam com base na versão do Microsoft Dynamics 365 implantada para sua organização.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Pré-requisitos se você usar o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (julho de 2017) 
Se o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017), foi implementado em sua organização, o administrador do sistema deve publicar o espaço de trabalho móvel **Gerenciamento de despesas**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

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
<td>Implementar o KB 4019015.</td>
<td>Administrador do sistema</td>
<td>O KB 4019015 é um hotfix de metadados ou de atualização X++ que contém o espaço de trabalho móvel <strong>Gerenciamento de despesas</strong>. Para implementar o KB 4019015, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crie um pacote implantável</a> que contenha os modelos <strong>ApplicationSuite</strong> e <strong>ExpenseMobile</strong> e carregue o pacote implantável no LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publique o espaço de trabalho móvel <strong>Gerenciamento de despesas</strong>.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Baixe e instale o aplicativo móvel Dynamics 365 for Operations
Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:

- [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel
1. Inicie o aplicativo móvel no seu dispositivo.
2. Insira sua URL do Dynamics 365.
4. Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.
5. Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.


[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Obtenha um recibo usando o espaço de trabalho móvel Gerenciamento de despesas

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de despesas**.
2. Selecione **Capturar recibo**.
3. Selecione **Tirar foto** ou **Escolher imagem**.
4. Siga uma destas etapas:

    - Se você selecionou **Tirar foto**, siga estas etapas:

        1. Utilize a câmera de seu dispositivo móvel, para que você possa tirar uma foto do recibo. Quando terminar de tirar uma foto, selecione **OK** para aceitar a foto.
        2. Opcional: Insira um nome para a foto e observações.

    - Se você tiver selecionado **Escolher imagem**, siga estas etapas:

        1. Selecione uma imagem na lista.
        2. Opcional: Insira um nome para a image e insira observações.

5. Selecione **Concluído**.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Inserir rapidamente as despesas usando o espaço de trabalho móvel Gerenciamento de despesas
1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de despesas**.
2. Selecione **Entrada rápida de despesas**.
3. Selecione a categoria da despesa. Você verá uma lista de categorias de despesas que estão carregadas para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se a categoria não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por categoria de despesa ou alterne para pesquisar por tipo de despesa.
4. Insira a data da transação da despesa.
5. Opcional: Insira o comerciante da despesa.
6. Insira o valor da despesa.
7. Selecione a moeda da despesa. Você verá uma lista de códigos de moeda que são carregados para seu aplicativo para uso offline. Por padrão, 400 moedas são carregadas, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se a sua moeda não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por moeda ou alterne para pesquisar por nome de categoria.
8. Selecione **Tirar foto** ou **Escolher imagem**.
9. Siga uma destas etapas:

    - Se selecionou **Tirar foto**, utilize a câmera de seu dispositivo móvel, para tirar uma foto do recibo. Quando terminar de tirar uma foto, selecione **OK** para aceitar a foto.
    - Se você tiver selecionado **Escolher imagem**, selecione uma imagem na lista.

10. Selecione **Concluído**.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Aprovar um relatório de despesas usando o espaço de trabalho móvel Gerenciamento de despesas (caso você use a atualização de julho de 2017)
1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de despesas**.
2. **Aprovações de despesas** mostra o número de relatórios de despesas atribuídos a você para aprovação. O número é atualizado a cada 30 minutos, aproximadamente. Selecione **Aprovações de despesas**.

    A lista de relatórios de despesas atribuídos a você para aprovação é mostrada.
    
3. Selecione um relatório de despesas para exibir os detalhes de despesa para ele.
4. Selecione uma despesa para exibir seus detalhes. As informações mostradas para uma despesa incluem todos os detalhes sobre recibos, convidados e discriminações.
5. De volta à página **Relatório de despesas**, selecione aprovar ou rejeitar o relatório de despesas.
6. Insira comentários sobre a ação de aprovação.
7. Selecione **Concluído**.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Crie um novo relatório de despesas e o envie para aprovação usando o espaço de trabalho Gerenciamento de despesas (caso você use a atualização de julho de 2017)
1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de despesas**.
2. Selecione **Entrada de despesas**.
3. Selecione **Novo relatório** ou selecione um relatório de despesas existente na lista.
4. Para novos relatórios de despesas, insira a finalidade e qualquer informação adicional que esteja disponível. Essas informações variam dependendo da forma que o gerenciamento de despesas está configurado para sua empresa.
5. Selecione **Concluído**.
6. Para adicionar despesas existentes ao relatório de despesas, como transações de cartão de crédito, selecione **Anexar**.
7. Selecione uma ou mais despesas na lista.
8. Selecione **Concluído**.
9. Para adicionar uma nova despesa ao relatório de despesas, selecione **Nova despesa**.
10. Selecione a categoria da despesa. Você verá uma lista de categorias de despesas que estão carregadas para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se a categoria não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por categoria de despesa ou alterne para pesquisar por tipo de despesa.
11. Opcional: Insira o comerciante da despesa.
12. Insira a data da transação da despesa.
13. Insira o valor da despesa.
14. Selecione a moeda da despesa. Você verá uma lista de códigos de moeda que são carregados para seu aplicativo para uso offline. Por padrão, 400 moedas são carregadas, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se a sua moeda não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por moeda ou alterne para pesquisar por nome de categoria.
15. Selecione **Concluído**.
16. Para adicionar mais detalhes à despesa, selecione **Adicionar mais detalhes**. Os campos disponíveis dependerão da configuração de gerenciamento de despesas para sua empresa.
17. Se a política da empresa exigir um recibo pela despesa, selecione **Recibos** e então siga estas etapas:

    1. Selecione **Capturar recibo** ou **Anexar recibo**.
    2. Siga uma destas etapas:

        - Caso você tenha selecionado **Capturar recibo**, siga estas etapas:

            1. Selecione **Tirar foto** ou **Escolher imagem**.
            2. Siga uma destas etapas:

                - Se você selecionou **Tirar foto**, siga estas etapas:

                    1. Utilize a câmera de seu dispositivo móvel, para que você possa tirar uma foto do recibo. Quando terminar de tirar uma foto, selecione **OK** para aceitar a foto.
                    2. Opcional: Insira um nome para a foto e observações.

                - Se você tiver selecionado **Escolher imagem**, siga estas etapas:

                    1. Selecione uma imagem na lista.
                    2. Opcional: Insira um nome para a image e insira observações.

            3.  Selecione **Concluído**.

        - Caso você tenha selecionado **Anexar recibo**, siga estas etapas:

            1.  Selecione uma ou mais imagens na lista.
            2.  Selecione **Concluído**.

    3. Selecione o botão **Voltar** para retornar aos detalhes da despesa.

18. Se a política da empresa exigir os convidados incluídos na despesa, selecione **Convidados** e então siga estas etapas:

    1. Selecione **Convidado**, **Convidados anteriores** ou **Colegas de trabalho**.
    2. Siga uma destas etapas:

        - Caso você tenha selecionado **Convidado**, siga estas etapas:

            1. Insira o nome do convidado
            2. Opcional: insira a organização e/ou o país do convidado.
            3. Opcional: insira o cargo do convidado.
            4. Selecione **Concluído**.

        - Caso você tenha selecionado **Convidados anteriores**, siga estas etapas:

            1. Selecione um ou mais convidados anteriores na lista. Você verá uma lista de convidados anteriores adicionados a relatórios de despesas anteriores carregados em seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se o seu convidado anterior não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por nome ou alterne para a pesquisa por organização, país ou cargo.
            2. Selecione **Concluído**.

        - Caso você tenha selecionado **Colegas de trabalho**, siga estas etapas:

            1. Selecione um ou mais colegas de trabalho na lista. Você verá uma lista de colegas de trabalho carregada em seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se o seu colega de trabalho não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por nome ou alterne para a pesquisa por empresa ou cargo.
            2. Selecione **Concluído**.

    3. Selecione o botão **Voltar** para retornar aos detalhes da despesa.

19. Se a política da empresa exigir que a empresa seja discriminada, selecione **Discriminar** e então siga estas etapas:

    1. Selecione a data inicial a ser discriminada.
    2. Selecione **Adicionar discriminação**.
    3. Selecione a subcategoria da discriminação de despesas. Você verá uma lista de subcategorias de despesas carregada em seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se a subcategoria não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online. Pesquise por nome de subcategoria de despesas.
    4. Insira o valor da transação na discriminação.
    5. Edite a data da transação, se necessário.
    6. Selecione **Concluído**.
    7. Repita as etapas anteriores até adicionar todas as discriminações na data selecionada.
    8. Para outros dias, selecione **Copiar para o dia seguinte** para copiar as discriminações para o dia seguinte. Como alternativa, você pode selecionar a data a ser discriminada e então adicionar as discriminações como fez para a primeira data.
    9. Depois de concluir a discriminação da despesa, selecione o botão **Voltar** para retornar aos detalhes da despesa.

20. Selecione o botão **Voltar** para retornar à página **Relatório de despesas**.
21. Repita as etapas anteriores até adicionar todas as despesas.
22. Selecione **Enviar**.
23. Insira comentários para o aprovador.
24. Selecione **Concluído**.

