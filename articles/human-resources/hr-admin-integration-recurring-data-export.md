---
title: Criar um aplicativo de exportação de dados recorrente
description: Este artigo mostra como criar um aplicativo lógico de Microsoft Azure que exporta dados da Microsoft Dynamics 365 Human Resources em um plano recorrente.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cef9e7f78646a4a5794eb14a9f1ad355768480644504c548afbb32e23fff4cd5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744861"
---
# <a name="create-a-recurring-data-export-app"></a>Criar um aplicativo de exportação de dados recorrente

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo mostra como criar um aplicativo lógico de Microsoft Azure que exporta dados da Microsoft Dynamics 365 Human Resources em um plano recorrente. O tutorial tira proveito da interface de programação de aplicativo (API) REST de recursos humanos para exportar os dados. Depois que os dados tiverem sido exportados, o aplicativo lógico salva o pacote de dados exportados em uma pasta Microsoft OneDrive for Business.

## <a name="business-scenario"></a>Cenário de negócios

Em um cenário comercial típico para integrações do Microsoft Dynamics 365, os dados devem ser exportados para um sistema downstream em um plano recorrente. Este tutorial mostra como exportar todos os registros de trabalhador da Microsoft Dynamics 365 Human Resources e salvar a lista de trabalhadores em uma pasta OneDrive for Business.

> [!TIP]
> Os dados específicos que são exportados neste tutorial e o destino dos dados exportados são apenas exemplos. Você pode alterá-las facilmente para atender às suas necessidades comerciais.

## <a name="technologies-used"></a>Tecnologias usadas

Este tutorial usa as seguintes tecnologias:

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**– A fonte de dados mestre dos trabalhadores que serão exportados.
- **[Aplicativos lógicos do Azure](https://azure.microsoft.com/services/logic-apps/)** – A tecnologia que fornece orquestração e programação da exportação recorrente.

    - **[Conectores](/azure/connectors/apis-list)** – A tecnologia usada para conectar o aplicativo lógico às empresas requeridas.

        - [HTTP com conector Azure AD](/connectors/webcontents/)
        - Conector [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness)

- **[API REST do pacote DMF](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – A tecnologia usada para disparar a exportação e monitorar seu progresso.
- **[OneDrive for Business](https://onedrive.live.com/about/business/)** – O destino dos trabalhadores exportados.

## <a name="prerequisites"></a>Pré-requisitos

Antes de iniciar o exercício neste tutorial, você deve ter os seguintes itens:

- Um ambiente de Human Resources que tem permissões de nível de administrador no ambiente
- Uma [Assinatura do Azure](https://azure.microsoft.com/free/) para hospedar o aplicativo lógico

## <a name="the-exercise"></a>O exercício

Depois de concluir este exercício, você terá um aplicativo lógico conectado ao seu ambiente de Human Resources e à sua conta do OneDrive for Business. O aplicativo lógico exporta um pacote de dados de recursos humanos, aguarda a conclusão da exportação, faz o download do pacote de dados exportados e salva o pacote de dados na pasta OneDrive for Business que você especificou.

O aplicativo lógico concluído será semelhante à ilustração a seguir.

![Visão geral do aplicativo lógico.](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>Etapa 1: Criar um projeto de exportação de dados em recursos humanos

Em Human Resources, crie um projeto de exportação de dados que exporta trabalhadores. Nomeie o projeto **Exportar trabalhadores**, e certifique-se de que a opção **Gerar pacote de dados** está definida como **Sim**. Adicione uma única entidade (**Trabalhador**) ao projeto e selecione o formato a ser exportado. (O formato Microsoft Excel é usado neste tutorial.)

![Projeto de dados de exportação de trabalhadores.](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Lembre o nome do projeto de exportação de dados. Você precisará delas quando criar o aplicativo lógico na próxima etapa.

### <a name="step-2-create-the-logic-app"></a>Etapa 2: Criar o aplicativo lógico

A maior parte do exercício envolve a criação do aplicativo lógico.

1. No portal do Azure, crie um aplicativo lógico.

    ![Página de criação lógica de aplicativo.](media/integration-logic-app-creation-1.png)

2. No designer de aplicativos lógicos, comece com um aplicativo lógico em branco.
3. Adicione um [Disparador de agenda recorrência](/azure/connectors/connectors-native-recurrence) para executar o aplicativo lógica a cada 24 horas (ou de acordo com um plano de sua escolha).

    ![Caixa de diálogo de recorrência.](media/integration-logic-app-recurrence-step.png)

4. Chame a API REST de DMF [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) para programar a exportação de seu pacote de dados.

    1. Use a ação **Invocar uma solicitação HTTP** do HTTP com conector Azure AD.

        - **URL do recurso básico:** A URL do seu ambiente de Human Resources (não inclui informações de caminho/namespace).
        - **Azure AD URI do Recurso:** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > O serviço de Human Resources ainda não fornece um conector que expõe todas as APIs que compõem a API REST do pacote DMF, como **ExportToPackage**. Em vez disso, você deve chamar as APIs usando solicitações HTTPS brutas por meio do HTTP com o conector Azure AD. Esse conector usa Azure Active Directory (Azure AD) para autenticação e autorização para Human Resources.

        ![HTTP com conector Azure AD.](media/integration-logic-app-http-aad-connector-step.png)

    2. Faça login no seu ambiente de Human Resources por meio do HTTP com o conector Azure AD.
    3. Configure uma solicitação HTTP **LANÇAR** para chamar a API REST de DMF **ExportToPackage**.

        - **Método:** LANÇAR
        - **URL da solicitação:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **Corpo da solicitação:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Invocar uma ação de solicitação HTTP.](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > Você pode desejar renomear cada etapa para que seja mais significativo do que o nome padrão, **Invocar uma solicitação HTTP**. Por exemplo, você pode renomear essa etapa **ExportToPackage**.

5. [Inicialize uma variável](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) para armazenar o status de execução da solicitação **ExportToPackage**.

    ![Inicializar ação variável.](media/integration-logic-app-initialize-variable-step.png)

6. Aguarde até que o status da execução da exportação de dados seja **Bem-sucedido**.

    1. Adicione um [Até loop](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) que se repita até que o valor da variável **ExecutionStatus** seja **Bem-sucedido**.
    2. Adicionar uma ação de **Atraso** que aguarda cinco segundos antes de sondar o status de execução atual da exportação.

        ![Até contêiner de loop.](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Defina a contagem de limite como **15** para aguardar um máximo de 75 segundos (15 iterações × 5 segundos) para a exportação ser concluída. Se a exportação levar mais tempo, ajuste a contagem de limites conforme apropriado.        

    3. Adicione uma ação **Invocar solicitação HTTP** para chamar a API REST de DMF [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus), e definir a variável **ExecutionStatus** ao resultado da resposta **GetExecutionSummaryStatus**.

        > Este exemplo não faz a verificação de erros. A API **GetExecutionSummaryStatus** pode retornar estados de terminal sem êxito (ou seja, estados diferentes de **Bem-sucedido**). Para obter mais informações, consulte a [documentação do API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).

        - **Método:** LANÇAR
        - **URL da solicitação:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **Corpo da solicitação:** body('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > Talvez seja necessário inserir o **Corpo da solicitação** no modo de exibição de código ou no editor de funções no designer.

        ![Invocar uma ação de solicitação 2 HTTP.](media/integration-logic-app-get-execution-status-step.png)

        ![Definir ação variável.](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > O valor da ação **Definir variável** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) será diferente do valor para o valor de corpo **Invocar uma solicitação HTTP 2**, embora o designer mostre os valores da mesma forma.

7. Obter a URL de download do pacote exportado.

    - Adicione uma ação **Invocar solicitação HTTP** para chamar a API REST do DMF [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).

        - **Método:** LANÇAR
        - **URL da solicitação:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **Corpo da solicitação:** {"executionId": body('GetExportedPackageURL')?['value']}

        ![Ação GetExportedPackageURL.](media/integration-logic-app-get-exported-package-step.png)

8. Baixe o pacote exportado.

    - Adicione uma solicitação HTTP **OBTER** (uma ação de conector [HTTP integrada](/azure/connectors/connectors-native-http)) para baixar o pacote da URL que foi retornada na etapa anterior.

        - **Método:** OBTER
        - **URI:** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > Talvez seja necessário inserir o **URI** no modo de exibição de código ou no editor de funções no designer.

        ![Ação do SQL.](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > Essa solicitação não exige nenhuma autenticação adicional, porque a URL que a **GetExportedPackageUrl** retorna inclui um token de assinaturas de acesso compartilhado que concede acesso ao download do arquivo.

9. Salve o pacote baixado usando o conector do [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness).

    - Adicione uma ação [Criar arquivo](/connectors/onedriveforbusinessconnector/#create-file) do OneDrive for Business.
    - Conecte sua conta do OneDrive for Business, conforme necessário.

        - **Caminho da pasta:** Uma pasta escolhida
        - **Nome do arquivo:** worker\_package.zip
        - **Conteúdo do arquivo:** O corpo da etapa anterior (conteúdo dinâmico)

        ![Criar ação de arquivo.](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>Etapa 3: Testar o aplicativo lógico

Para testar seu aplicativo lógico, selecione o botão **Executar** no designer. Você verá que as etapas do aplicativo lógico começam a ser executadas. Após 30 a 40 segundos, o aplicativo lógico deve concluir a execução, e sua pasta OneDrive for Business deve incluir um novo arquivo de pacote que contém os trabalhadores exportados.

Se uma falha for relatada em qualquer etapa, selecione a etapa com falha no designer e examine os campos de **Entradas** e **Saídas** da falha. Depure e ajuste a etapa conforme necessário para corrigir os erros.

A ilustração a seguir mostra como o designer de aplicativos lógico é parecido quando todas as etapas do aplicativo lógico são executadas com êxito.

![Execução bem-sucedida de aplicativo lógico.](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Resumo

Neste tutorial, você aprendeu a usar um aplicativo lógico para exportar dados de recursos humanos e salvar os dados exportados em uma pasta OneDrive for Business. Você pode modificar as etapas deste tutorial conforme necessário para atender às suas necessidades comerciais.




[!INCLUDE[footer-include](../includes/footer-banner.md)]