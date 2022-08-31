---
title: Gerar relatórios de Serviços de Saúde Acessíveis no gerenciamento de benefícios
description: Este artigo descreve como o Gerenciamento de benefícios rastreia informações relatadas no Formulário 1095-B e no Formulário 1095-C para a carta de ordem de empregador da ACA (Affordable Care Act).
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a56fe2b3a25a300687d81702c52614a78f2a6f61
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336831"
---
# <a name="generate-aca-reports-in-benefits-management"></a>Gerar relatórios de ACA no gerenciamento de benefícios

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O gerenciamento de benefícios rastreia informações relatadas no Formulário 1095-B e no Formulário 1095-C para o mandato de empregador da Affordable Care Act (ACA - Lei de Serviços de Saúde Acessíveis). Como o recurso de relatório da ACA no espaço de trabalho **Benefícios** anterior, essa funcionalidade se aplica somente a entidades legais nos Estados Unidos.

Para usar essa funcionalidade, você deve primeiro ativar o **Gerenciamento Avançado de Benefícios**. Para obter mais informações, incluindo advertências importantes sobre o gerenciamento de benefícios, consulte [Habilitar ou desabilitar o gerenciamento de benefícios](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Você pode usar o relatório da ACA somente no espaço de trabalho de **Gerenciamento de benefícios** ou no espaço de trabalho de **Benefícios** antigo, não em ambos. Por exemplo, se você alternou para o gerenciamento de benefícios, o relatório da ACA estará disponível somente no espaço de trabalho **Gerenciamento de benefícios** e não no espaço de trabalho de **Benefícios** antigo.
>
> Se você alternar para o gerenciamento de benefícios no meio de um ano de inscrição, deverá configurar corretamente dados do funcionário para o ano inteiro no gerenciamento de benefícios. Dessa forma, você garante que receberá informações precisas sobre relatórios de todo o ano.

## <a name="getting-started"></a>Introdução

Para rastrear informações de formulários 1095, primeiro crie um ou mais grupos de cobertura de Serviços de Saúde Acessíveis. Esses grupos indicam as seguintes informações:

- A oferta de cobertura que foi fornecida a um funcionário
- A participação do funcionário com prêmio mensal de menor custo se o custo estiver acima da linha de pobreza estabelecida pelo governo
- O safe harbor que é usado pelo empregador, se aplicável

Os grupos de cobertura de Serviços de Saúde Acessíveis ajudam você a gerenciar essas informações para vários registros de funcionários que têm as mesmas condições. Você facilmente pode atribuir grupos a um ou mais funcionários.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Criar ou editar um grupo de cobertura de Serviços de Saúde Acessíveis

1. No espaço de trabalho **Gerenciamento de benefícios**, selecione **grupo de cobertura de Serviços de Saúde Acessíveis**.

    ![Selecionar grupo de cobertura de Serviços de Saúde Acessíveis.](./media/hr-benefits-management-aca-coverage-group.png)

2. Selecione **Novo** para criar um novo grupo de cobertura de Serviços de Saúde Acessíveis ou **Editar** para alterar um grupo existente.

    ![Selecionar Novo ou Editar.](./media/hr-benefits-management-aca-new.png)

3. Defina os campos a seguir.

    | Campo | descrição |
    |---|---|
    | Organização | Insira um nome para o grupo. |
    | Descrição | Insira uma descrição do grupo. |
    | Oferta de cobertura | A cobertura oferecida aos funcionários, o cônjuge ou parceiro e dependentes. |
    | Cota de custo do funcionário | O valor pelo qual o funcionário é responsável. |
    | Seção 4980H Safe Harbor aplicável | O código de compensação de transição ou safe harbor do 4980H. |
    | Mês de início do plano | Selecione o mês do calendário quando começa o ano do plano de benefícios. |
    | Grupo válido desde | A primeira data em que este registro é válido. |
    | Grupo válido até | A última data em que este registro é válido. Se não houver data de validade, digite **Nunca**. |

    ![Criar um grupo de cobertura.](./media/hr-benefits-management-aca-new-group.png)

4. Selecione **Salvar**.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Atribuir vários funcionários a um grupo de cobertura de Serviços de Saúde Acessíveis

1. No espaço de trabalho **Gerenciamento de benefícios**, selecione **grupo de cobertura de Serviços de Saúde Acessíveis**.
2. Selecione o grupo ao qual funcionários serão atribuídos.
3. Selecione **Atribuição em massa**.

    ![Selecionar Atribuição em massa.](./media/hr-benefits-management-aca-mass-assignment.png)

4. Selecione funcionários na lista e, em seguida, **Atribuir**.

    ![Atribuir funcionários selecionados a um grupo.](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Manter várias versões de opções de cobertura

Você pode manter várias versões de qualquer grupo de cobertura. Quando algo é alterado em sua organização ou nos benefícios oferecidos, você pode manter as informações do grupo atualizadas sem precisar criar um novo grupo e reatribuir funcionários a ele.

Depois de criar grupos de cobertura de Serviços de Saúde Acessíveis, você pode atribuir funcionários a eles em massa. Você também pode atribuir funcionários a grupos individualmente e indicar se as informações de ACA são rastreadas e relatadas.

Se não for necessário rastrear e relatar informações de ACA de um funcionário, você poderá definir a opção **Cobertura de relatório** como **Não**. Por exemplo, você pode ter funcionários de meio expediente que não exigem relatórios de ACA.

### <a name="override-default-values-for-an-employee"></a>Substituir valores padrão para um funcionário

Para os funcionários atribuídos a um grupo de cobertura de Serviços de Saúde Acessíveis, você pode alterar as seguintes opções para todos os meses que exigem valores diferentes:

- Oferta de cobertura
- Cota de custo do funcionário
- Seção 4980H Safe Harbor aplicável

> [!NOTE]
> Para relatórios de 2020 ACA, você deve relatar os dois CEPs de trabalho e residencial no formulário 1095-C. Os valores são preenchidos automaticamente, com base nos locais ativos atuais. Se um local for diferente durante parte do ano, você deverá substituir o valor. O campo **CEP** (linha 17) do relatório 1095-C só será preenchido se o código **Oferta de cobertura** contiver **1L** até **1Q**, da seguinte maneira:
>
> - **1L, 1M ou 1N:** o CEP de residência principal
> - **1O, 1P, 1Q:** o CEP do trabalho principal

Para inserir exceções para valores de um grupo de cobertura de Serviços de Saúde Acessíveis, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links** e, depois, **Trabalhadores**.
2. Selecione o funcionário na lista.
3. Na guia **Emprego**, na seção **Mais informações**, selecione **Cobertura de Serviços de Saúde Acessíveis**.

    ![Alterar opções para um funcionário.](./media/hr-benefits-management-aca-change-single-employee.png)

4. Selecione **Editar**.
5. Para cada mês que exija alterações, marque a caixa de seleção **Substituir padrão** e altere os outros valores, conforme necessário.

    ![Substituir valores padrão.](./media/hr-benefits-management-aca-override-default.png)

6. Selecione **Salvar**.

## <a name="report-health-care-coverage"></a>Relatar cobertura do plano de saúde

Você deve rastrear qualquer cobertura de plano de saúde autossegurada, patrocinada pelo empregador, para funcionários de tempo integral e meio expediente. Inclua cada funcionário, junto com os dependentes, no relatório 1095-C para os meses em que foram cobertos.

Para indicar se um plano de benefícios deve ser relatado, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de benefícios**, selecione **Planos de benefícios**.
2. Selecione o plano de benefícios a ser relatado.
3. Selecione **Editar**.
4. Defina a opção **Relatado segundo a Lei de Serviços de Saúde Acessíveis** como **Sim**.

    ![Relatórios de cobertura do plano de saúde.](./media/hr-benefits-management-aca-report-coverage.png)

5. Selecione **Salvar**.

Se um funcionário escolher a cobertura de plano de saúde para um dependente, o período de cobertura do dependente será determinado pela data em que o dependente foi inscrito ou removido. As datas de cobertura para os dependentes são calculadas automaticamente com base no período em que o dependente estava qualificado e ativo em um plano durante o ano de inscrição.

## <a name="generate-1095-b-and-1095-c-forms"></a>Gerar formulários 1095-B e 1095-C

Você pode gerar formulários 1095-B e 1095-C da ACA e distribuí-los a cada um dos funcionários. Você também pode gerar eletronicamente o formulário 1095-C e os arquivos de transmissão 1094-C correspondentes para enviar ao Serviço da Receita Federal (IRS).

1. No espaço de trabalho **Gerenciamento de benefícios**, selecione **Formulário 1095-B da ACA** ou **Formulário 1095-C da ACA**.
2. Altere os parâmetros conforme necessário e, depois, selecione **OK**.

    > [!NOTE]
    > Se você estiver imprimindo formulários 1095-C para mais de 500 funcionários, receberá mais de um arquivo PDF. É recomendável aumentar o valor do campo **Tamanho máximo de arquivo em megabytes** na página **Parâmetros de gerenciamento de documentos** para **150**. (Para abrir rapidamente essa página, você pode usar o campo de pesquisa na barra de navegação.)
    >
    > ![Alterar o tamanho máximo do arquivo.](./media/hr-benefits-management-aca-maximum-file-size.png)

3. Para verificar o status dos relatórios e exibi-los, use o campo de pesquisa na barra de navegação para abrir a página **Trabalhos de relatórios eletrônicos**.

    ![Pesquisar a página Trabalhos de relatórios eletrônicos.](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Selecione o relatório a ser exibido e, depois, selecione **Mostrar arquivos**.

    ![Mostrar arquivos.](./media/hr-benefits-management-aca-show-files.png)

5. Selecione **Abrir**.

    ![Abrir um arquivo.](./media/hr-benefits-management-aca-open-file.png)

6. Na barra de notificação que aparece na parte inferior da janela do navegador, abra o arquivo zip e selecione o relatório. Você pode exibir ou imprimir o arquivo PDF.

    ![Formulário de exemplo 1095-C.](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>Exibir informações de cobertura de ACA

A página **Cobertura de Serviços de Saúde Acessíveis do Trabalhador** mostra as seguintes informações:

- Funcionários atribuídos a cada grupo de cobertura
- Funcionários que não precisam ser incluídos em um relatório
- Funcionários não atribuídos

Para exibir estas informações, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de benefícios**, selecione **Cobertura de Serviços de Saúde Acessíveis do Trabalhador**.
2. No campo **Nome do grupo**, selecione um grupo.

    ![Exibir cobertura de ACA.](./media/hr-benefits-management-aca-view-coverage.png)

Se algum dos valores padrão do grupo de cobertura de Serviços de Saúde Acessíveis for substituído, um asterisco aparecerá ao lado do valor que foi alterado. Se os valores para todos os 12 meses forem iguais e não tiverem sido substituídos, o valor aparecerá na coluna **Todos os 12 meses**.

Você pode exibir funcionários que estão marcados como Não pode ser relatado segundo a ACA e que não precisarão de um formulário 1095-C. No campo **Filtrar por**, selecione **Não pode ser relatado segundo a ACA**.

Você pode exibir funcionários que não estão atribuídos a um grupo ou que estão atribuídos a um grupo expirado. No campo **Filtrar por**, selecione **Grupo não atribuído ou vencido**.

### <a name="export-to-excel"></a>Exportar para Excel

Para exportar uma das listas para o Microsoft Excel, siga estas etapas.

1. Selecione o botão **Abrir no Microsoft Office**.
2. Selecione **Tabela temporária de HCM do Human Resources para uso interno**.
3. Selecione **Baixar**.

### <a name="view-aca-reportable-dependents"></a>Exibir dependentes relatados segundo a ACA

Se você precisar relatar as pessoas cobertas porque fornece cobertura autossegurada, poderá exibir os dependentes que são cobertos por planos de benefícios marcados como **Pode ser relatado segundo a ACA**. No Painel de Ações, selecione **Exibir Cobertura de Dependentes**.

![Exibir cobertura de dependente.](./media/hr-benefits-management-aca-view-dependent-coverage.png)

As informações de cobertura dos dependentes do funcionário são mostradas.

![Cobertura de dependente.](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> A página mostra somente os planos de benefícios marcados como **Pode ser relatado segundo a ACA**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
