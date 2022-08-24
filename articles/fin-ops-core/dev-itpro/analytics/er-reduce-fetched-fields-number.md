---
title: Melhorar o desempenho de soluções ER, reduzindo o número de campos de tabela obtidos no runtime
description: Este artigo explica como você pode ajudar a melhorar o desempenho, reduzindo o número de campos de tabela obtidos no runtime.
author: kfend
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.custom: ''
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: 5c9481f1021a5dba6e1d4020bbf85a10bd551ac0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278816"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Melhorar o desempenho de soluções ER, reduzindo o número de campos de tabela obtidos no runtime

[!include[banner](../includes/banner.md)]

Você pode criar os [formatos](er-overview-components.md#format-components-for-outgoing-electronic-documents) de [relatórios eletrônicos](general-electronic-reporting.md) (ER) que geram documentos de saída em vários formatos. Quando um documento é gerado, um formato de ER chama as fontes de dados que foram configuradas em um [mapeamento de modelo](er-overview-components.md#model-mapping-component) de ER correspondente. Para configurar o acesso a tabelas de aplicação, consultas ou entidades para a recuperação do registro, você pode usar fontes de dados de ER do tipo *Registros de tabela* . Por padrão, uma fonte de dados do tipo *Registros de tabela* recupera os valores de todos os campos nos registros solicitados. No entanto, você pode configurar esse tipo de fonte de dados para que ela busque somente os valores de campo necessários para o formato ER em execução. Essa configuração ajuda a reduzir o consumo de memória do servidor de aplicações que executa a recuperação de dados e registra o cache adicional.

Para saber mais sobre como limitar a lista de campos obtidos de fontes de dados do tipo *Registros de tabela*, conclua o exemplo neste artigo.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Exemplo: reduz o número de campos de tabela obtidos no runtime

Os procedimentos a seguir mostram como um usuário na função de administrador do sistema ou de relatório eletrônico pode configurar um mapeamento de modelo ER para que ele busque somente os campos necessários para executar o formato ER, para ajudar a reduzir o consumo da memória do servidor de aplicações.

Estes procedimentos podem ser concluídos na empresa **USMF** no Microsoft Dynamics 365 Finance. Nenhum código é necessário.

Para concluir este exemplo, você deve ter acesso à empresa **USMF** para uma das seguintes funções:

- Consultor funcional de relatório eletrônico
- Administrador do sistema

Neste exemplo, você usará as [configurações](general-electronic-reporting.md#Configuration) do ER fornecidas para a empresa **Litware, Inc.** de exemplo. Verifique se o provedor de configuração da empresa **Litware, Inc.** (`http://www.litware.com`) de exemplo está listado na estrutura de ER e marcado como **Ativo**. Se esse provedor de configuração não estiver listado, ou se ele não estiver marcado como **Ativo**, siga as etapas em [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Siga as etapas em [Configurar a estrutura de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar o conjunto mínimo de parâmetros de ER. Você deve concluir essa configuração antes de começar a usar a estrutura de ER para modificar fontes de dados da solução ER fornecida.

### <a name="import-the-sample-er-configurations"></a>Importar o exemplo de configurações de ER

Se você ainda não tiver concluído o exemplo no artigo [Criar uma nova solução ER para imprimir um relatório personalizado](er-quick-start1-new-solution.md), baixe e armazene localmente os arquivos XML para as configurações da solução de ER fornecida a seguir.

| Descrição do conteúdo            | Nome do arquivo |
|--------------------------------|-----------|
| Configuração do modelo de dados de ER    | [Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| Configuração de mapeamento do modelo de ER | [Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| Configuração de formato ER        | [Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Siga estas etapas para carregar as configurações da solução ER fornecida para a instância do Finance.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Na página **Configurações**, importe a configuração do modelo de dados ER.

    1. Selecione **Troca** e, em seguida, **Carregar de um arquivo XML**.
    2. Selecione **Procurar** e localize e selecione o arquivo **Questionnaires model.version.1.xml**. Depois, selecione **OK**.

4. Importe a configuração de mapeamento de modelo ER.

    1. Selecione **Troca** e, em seguida, **Carregar de um arquivo XML**.
    2. Selecione **Procurar** e localize e selecione o arquivo **Questionnaires mapping.version.1.1.xml**. Depois, selecione **OK**.

5. Importe a configuração de formato de ER.

    1. Selecione **Troca** e, em seguida, **Carregar de um arquivo XML**.
    2. Selecione **Procurar** e localize e selecione o arquivo **Questionnaires format.version.1.1.xml**. Depois, selecione **OK**.

6. Na árvore de configuração, expanda o **Modelo de questionários**.
7. Revise a lista de configurações de ER importadas na árvore de configuração.

    ![Analise a lista de configurações de ER importadas na página Configurações.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>Revise o mapeamento do modelo ER fornecido

1. Na página **Configurações**, selecione **Mapeamento de questionários**.
2. No Painel de Ação, selecione **Designer**.
3. Na página **Modelo para mapeamento da fonte de dados**, selecione **Designer**.
4. Na página **Designer de mapeamento do modelo**, no Painel de Ações, selecione **Exibição de grupo** para ativar a exibição do **Grupo**.
5. No painel **Modelo de dados**, expanda **Questionário**.

    Note que a fonte de dados **Questionário** foi configurada para acessar a tabela de aplicações `KMCollection`.

6. No painel **Fontes de dados**, expanda **Registros de tabela** \> **Questionários** \> **Campos**.

    Observe quantos campos da tabela de aplicação `KMCollection` são expostos pela fonte de dados **Questionário** do tipo *Registros de tabela*.

    ![Revise o mapeamento de modelo fornecido na página Designer de mapeamento de modelos quando a exibição de Grupo estiver ativada.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. No Painel de Ações, selecione novamente **Exibição de grupo** para desativar o modo de exibição **Grupo** e selecione **Mostrar tudo** \> **Mostrar somente mapeado**.

    Observe que alguns campos da tabela de aplicações `KMCollection` são usados para preencher a lista de registros de  **Questionário** no modelo de dados ER:

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![Revise o mapeamento de modelo fornecido na página Designer de mapeamento de modelos quando a exibição de Grupo estiver desativada.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Ativar o rastreamento de desempenho de ER

Siga as etapas em [Ativar o rastreamento de desempenho ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) para definir os parâmetros de usuário ER que permitem o rastreamento da execução de componentes ER.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>Executar o formato ER fornecido usando o mapeamento de modelo fornecido

Siga as etapas em [Executar um formato criado a partir do ER](er-quick-start1-new-solution.md#RunFormatFromER) para executar o formato ER fornecido para um único questionário na página **Configurações**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Revisar o rastreamento de execução da primeira execução

1. Acesse **Administração da organização** \> **Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, expanda **Modelo de questionários** e selecione **Mapeamento de questionários**.

    > [!NOTE]
    > Os detalhes na FastTab **Versões** indicam que você selecionou a versão de rascunho da configuração de **Mapeamento de questionários**. Portanto, você pode modificar o conteúdo deste mapeamento de modelo.

3. No Painel de Ação, selecione **Designer**.
4. Na página **Modelo para mapeamento da fonte de dados**, selecione **Designer**.
5. Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.
6. Na caixa de diálogo **Configurações de resultado de rastreamento de desempenho**, selecione o rastreamento que foi gerado durante o último formato executado.

    ![Seleção do rastreamento na caixa de diálogo Configurações de resultado de rastreamento de desempenho.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Selecione **OK**. 
8. Na FastTab **Detalhes**, filtre o caminho do **Questionário** que aponta para a fonte de dados do **Questionário**.
9. Revise os detalhes da consulta de banco de dados que foi gerada quando a fonte de dado do **Questionário** foi chamada.

    Observe que todos os campos da tabela de aplicações `KMCollection` foram obtidos no runtime quando a fonte de dados do **Questionário** foi chamada.

    ![Revisar os detalhes da consulta de banco de dados na página Designer de mapeamento de modelo.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>Modificar o mapeamento do modelo ER fornecido

1. Na página **Designer de mapeamento de modelo**, no painel **Fontes de dados**, selecione a fonte de dados **Questionário**.
2. No painel **Fontes de dados**, selecione **Editar**.
3. Na caixa de diálogo **Propriedades da fonte de dados**, selecione **Selecionar campos** para especificar a lista de campos da tabela de aplicações `KMCollection` referenciada que será obtida no runtime quando a fonte de dados do **Questionário** editável for chamada.

    ![Selecione Selecionar campos na caixa de diálogo Propriedades da fonte de dados para começar a configurar a lista de campos que será obtida na tabela de aplicações usando a fonte de dados editável.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. Na página **Selecionar campos**, selecione **Preencher automaticamente**.

    A lista **Campos selecionados** é preenchida automaticamente, com base em artefatos pré-configurados do mapeamento de modelo. Todos os campos e relações da tabela referenciada que são mencionados em qualquer associação, fórmula ou fonte de dados do mapeamento de modelo são adicionados à lista.

    ![Configure a lista de campos que serão obtidos na tabela de aplicações na página Selecionar campos.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Selecione **Salvar** e feche a página **Selecionar campos**.
6. Selecione **OK** para armazenar as alterações feitas nas configurações da fonte de dados.
7. No Painel de Ações, selecione **Mostrar tudo**.

    Observe que a fonte de dados do **Questionário** agora mostra o texto **\<Fields are filtered\>**. Este texto indica que a fonte de dados foi configurada para obter um número limitado de campos da tabela de aplicações referenciada.

    ![Analise o mapeamento de modelo atualizado na página Designer de mapeamento de modelo.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. Selecione **Salvar** para armazenar as alterações feitas no mapeamento de modelo editável.

    > [!NOTE]
    > No tempo de execução, o ER analisa as relações adicionadas e adiciona todos os campos usados nelas para a consulta do banco de dados, mesmo que esses campos não tenham sido explicitamente adicionados à lista de campos obtidos no tempo de design.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>Execute o formato ER fornecido usando o mapeamento de modelo atualizado

Siga as etapas em [Executar um formato criado a partir do ER](er-quick-start1-new-solution.md#RunFormatFromER) para executar o formato ER fornecido para um único questionário na página **Configurações**.

### <a name="review-the-execution-trace-of-the-second-run"></a>Revise o rastreamento de execução da segunda execução

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, expanda **Modelo de questionários** e selecione **Mapeamento de questionários**.
3. No Painel de Ação, selecione **Designer**.
4. Na página **Modelo para mapeamento da fonte de dados**, selecione **Designer**.
5. Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.
6. Na caixa de diálogo **Configurações de resultado de rastreamento de desempenho**, selecione o rastreamento que foi gerado durante o último formato executado.
7. Selecione **OK**.
8. Na FastTab **Detalhes**, filtre o caminho do **Questionário** que aponta para a fonte de dados do **Questionário**.
9. Revise os detalhes da consulta de banco de dados que foi gerada quando a fonte de dado do **Questionário** foi chamada.

    Note que somente os campos necessários para preencher a fonte de dados foram obtidos no runtime da tabela de aplicações `KMCollection` quando a fonte de dados do **Questionário** foi chamada.

    > [!NOTE]
    > Alguns campos, como os campos para a ID da partição, a ID da área de dados e a ID do registro, são adicionados automaticamente pela estrutura de Gerenciamento de Dados da aplicação Finance.

    ![Revise os detalhes da consulta de banco de dados para o mapeamento de modelo atualizado na página Designer de mapeamento de modelo.](./media/er-reduce-fetched-fields-number-query2.png)

Você pode usar esta técnica para reduzir o número de registros obtidos quando precisa reduzir o consumo de memória pelo mapeamento do modelo de ER em execução e pelo formato ER.

## <a name="limitations"></a>Limitações

Ao limitar o número de campos obtidos para uma fonte de dados do tipo *Registros de tabela*, você não pode usar os métodos de uma tabela de aplicação à qual a fonte de dados se refere, pois os metadados da aplicação não fornecem informações sobre os campos de tabela necessários para chamar esses métodos.

## <a name="usage-notes"></a>Notas de uso

Embora o comando **Preencher automaticamente** adicione campos automaticamente, ele não exclui automaticamente campos adicionados anteriormente, mesmo que não sejam mais usados em associações, fórmulas e fontes de dados do mapeamento de modelo editável.

Quando você seleciona **Preencher automaticamente**, o ER analisa as associações, fórmulas e fontes de dados que o mapeamento de modelo editável tinha quando foi aberto para edição. Se você alterar associações, fórmulas e fontes de dados do mapeamento de modelo editável e desejar usar o comando **Preencher automaticamente**, feche o designer de mapeamento de modelos e reabra-o para editar o mapeamento de modelo. 

## <a name="additional-resources"></a>Recursos adicionais

- [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)
- [Solução de problemas de desempenho nas configurações ER](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
