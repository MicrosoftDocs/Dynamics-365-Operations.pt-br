---
title: Rastrear resultados gerados de relatórios e compará-los com os valores de linha de base
description: Este tópico explica como você pode comparar os resultados de relatórios de ER (relatório eletrônico) gerados com os valores de relatório da linha de base.
author: NickSelin
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: e4245f5951cc4891b378f2343a1563ced33bc937
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345831"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Rastrear resultados gerados de relatórios e compará-los com os valores de linha de base

[!include[banner](../includes/banner.md)]

Você pode rastrear os resultados dos formatos de ER que geram documentos eletrônicos de saída. Quando a geração de rastreamento estiver ativada (usando o parâmetro do usuário do ER **Executar em modo de depuração**), um novo registro de rastreamento será gerado no log de execução do formato de ER, cada vez que um relatório de ER for executado. Os seguintes detalhes serão armazenados em cada rastreamento gerado:

- Todos os avisos gerados pelas regras de validação
- Todos os erros gerados pelas regras de validação
- Todos os arquivos gerados que são armazenados como anexos do registro de rastreamento

Você pode armazenar arquivos de aplicativo de linhas de base individuais para qualquer formato de ER. Os arquivos são considerados de linha de base quando descrevem os resultados esperados dos relatórios que estão em execução. Se um arquivo de linha de base estiver disponível para um formato de ER executado enquanto a geração de rastreamento estava ativada, o rastreamento armazenará, além dos detalhes que foram mencionados anteriormente, o resultado da comparação do documento eletrônico gerado com o arquivo da linha de base. Em um clique, você também pode obter o documento eletrônico gerado e seu arquivo de linha de base em um arquivo zip único. Em seguida, você pode efetuar a comparação detalhada usando uma ferramenta externa, como WinDiff.

Você pode avaliar o rastreamento para analisar se os documentos eletrônicos gerados têm o conteúdo esperado. Você pode fazer essa avaliação em um ambiente de teste de aceitação do usuário (UAT) quando a base do código for alterada (por exemplo, quando você tiver migrado para uma nova instância do aplicativo, instalado pacotes de hotfix ou implantado modificações de código). Assim, você pode garantir que a avaliação não afeta a execução de relatórios de ER usados. Para muitos relatórios de ER, a avaliação poderá ser feita em modo automático.

Para saber mais sobre este recurso, execute as guias de tarefas **ER Gerar relatórios e comparar resultados (Parte 1)** e **ER Gerar relatórios e comparar resultados (Parte 2)**, que fazem parte do processo de negócios **7.5.4.3 Testar serviços/soluções de TI (10679)** e podem ser baixados do [Centro de Download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Essas guias de tarefas o direcionam pelo processo de configuração da estrutura de ER para usar arquivos da linha de base para avaliar documentos eletrônicos gerados.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Exemplo: Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base

Este processo explica como configurar a estrutura do ER para coletar informações sobre definições de formato do ER e avaliar os resultados dessas execuções. Como parte da avaliação, os documentos gerados são comparados aos arquivos da linha de base. Neste exemplo, você criará as configurações do ER necessárias para a empresa de exemplo, Litware, Inc. Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando qualquer conjunto de dados.

Para concluir as etapas deste exemplo, primeiro conclua as etapas em [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, verifique se o provedor de configuração para a empresa de exemplo Litware, Inc. está listado e marcado como **Ativo**. Caso não veja este provedor de configuração, siga as etapas de [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-document-management-parameters"></a>Configurar parâmetros de gerenciamento de documentos

1. Vá para **Administração da organização** \> **Gerenciamento de documentos** \> **Tipos de documento** e crie um novo tipo de documento para armazenar arquivos de linha de base.
2. No campo **Classe**, insira **Anexar arquivo**.
3. No campo **Grupo**, insira **Arquivo**.

![Página Tipos de documento.](media/GER-BaselineSample-SetupDocumentType.PNG "Captura de tela da página Tipos de documento")

> [!NOTE]
> Um novo tipo de documento que tem o mesmo nome deve ser configurado para cada conjunto de dados em que você pretende usar o recurso de linha de base do ER.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Configurar parâmetros do ER para começar a usar o recurso de linha de base

1. No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.

    ![Espaço de trabalho de relatório eletrônico.](media/GER-BaselineSample-ERWorkspace.PNG "Captura de tela do espaço de trabalho Relatório eletrônico")

2. Na guia **Anexos**, no campo **Linha de base**, insira ou selecione o tipo de documento que você acabou de criar.

    ![Guia Anexos da página Parâmetros de Relatório eletrônico.](media/GER-BaselineSample-ERParameters.PNG "Captura de tela dos parâmetros de Relatório eletrônico")

3. Selecione **Salvar** e feche a página **Parâmetros de relatório eletrônico**.

### <a name="add-a-new-er-model-configuration"></a>Adicionar uma nova configuração de modelo de ER

1. No espaço de trabalho **Relatório eletrônico**, na seção **Configurações**, selecione o bloco **Configurações de relatórios**.
2. No Painel de Ações, selecione **Criar configuração**.
3. Na caixa de diálogo suspensa, no campo **Nome** , insira **Modelo para aprender linhas de base de ER**.
4. Selecione **Criar configurações** para confirmar a criação de uma nova entrada do modelo de dados de ER.

![Caixa de diálogo suspensa Criar configuração.](media/GER-BaselineSample-ModelAdd.PNG "Captura de tela da caixa de diálogo suspensa Criar configuração")

### <a name="design-a-data-model"></a>Crie um modelo de dados

1. Na página **Configurações**, no Painel de Ações, selecione **Designer**.
2. Selecione **Novo**.
3. Na caixa de diálogo suspensa, no campo **Nome** , digite **Raiz**.
4. Selecione **Adicionar**.
5. Selecione **Referência raiz**.
6. Selecione **OK** e, depois, **Salvar**.
7. Feche a página **Designer de modelo**.
8. Selecione **Alterar status**.
9. Selecione **Concluir** e, depois, **OK**.

![Página Configurações.](media/GER-BaselineSample-ModelComplete.PNG "Captura de tela da página Configurações")

### <a name="add-a-new-er-format-configuration"></a>Adicionar uma nova configuração de formato de ER

1. Na página **Configurações**, no Painel de Ações, selecione **Criar configuração**.
2. Na caixa de diálogo suspensa, no grupo do campo **Novo**, selecione **Formato baseado no modelo de dados Modelo para aprender linhas de base de ER**.
3. No campo **Nome**, insira **Formato para aprender linhas de base de ER**.
4. Selecione **Criar configurações** para confirmar a criação de uma nova entrada de formato de ER.

![Caixa de diálogo suspensa Criar configuração.](media/GER-BaselineSample-FormatAdd.PNG "Captura de tela da caixa de diálogo suspensa Criar configuração")

### <a name="design-a-format"></a>Criar um formato

Para este exemplo, você criará um formato simples de ER para gerar documentos XML.

1. Na página **Configurações**, no Painel de Ações, selecione **Designer**.
2. Selecione **Adicionar raiz**.
2. Na caixa de diálogo suspensa, siga estas etapas:

    1. Na árvore, selecione **Comum\\Arquivo**.
    2. No campo **Nome**, digite **Saída**.
    3. Selecione **OK**.

3. Selecione **Adicionar**.
4. Na caixa de diálogo suspensa, siga estas etapas:

    1. Na árvore, selecione **XML\\Elemento**.
    2. No campo **Nome**, digite **Documento**.
    3. Selecione **OK**.

5. Na árvore, selecione **Saída\\Documento**.
6. Selecione **Adicionar**.
7. Na caixa de diálogo suspensa, siga estas etapas:

    1. Na árvore, selecione **XML\\Atributo**.
    2. No campo **Nome**, insira **ID**.
    3. Selecione **OK**.

    ![Página do designer de formatos.](media/GER-BaselineSample-FormatLayoutDesign.PNG "Captura de tela da página Designer de formato")

8. Na guia **Mapeamento**, selecione **Excluir**.
9. Selecione **Adicionar raiz**.
10. Na caixa de diálogo suspensa, na árvore, selecione **Geral\\Parâmetro de entrada do usuário** e siga estas etapas:

    1. No campo **Nome**, insira **ID**.
    2. No campo **Etiqueta**, digite **Inserir ID**.
    3. Selecione **OK**.

11. Na árvore, selecione **Saída\\Documento\\Id**.
12. Selecione **Associar** e, depois, **Salvar**.

![Página do designer de formatos.](media/GER-BaselineSample-FormatMappingDesign.PNG "Captura de tela da página Designer de formato")

Com base na estrutura criada, o formato configurado gerará um arquivo XML. Este XML contém o elemento **Raiz** que tem o atributo **ID** definido para o valor que o usuário insere na caixa de diálogo de tempo de execução de ER.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Gere um novo arquivo de linha base para um formato de ER criado

1. Na página **Configurações**, na Guia Rápida **Versões**, selecione **Executar**.
2. No campo **Inserir ID**, digite **1**.
3. Selecione **OK**.

    ![Caixa de diálogo Parâmetros de relatório eletrônico.](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "Captura de tela da caixa de diálogo Parâmetros de Relatório eletrônico")

4. Salve uma cópia local do arquivo **out.Admin.xml** gerado para poder usá-lo posteriormente como uma linha de base para este formato de ER.

    ![Notificação sobre o arquivo gerado na página Configurações.](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "Captura de tela da notificação sobre o arquivo gerado na página Configurações")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Configurar parâmetros do ER para usar o recurso de linha de base

1. Na página **Configurações**, no Painel de Ações, na guia **Configurações**, selecione **Parâmetros de usuário**.
2. Defina a opção **Executar no modo de depuração** como **Sim**.
3. Selecione **OK**.

![Caixa de diálogo de parâmetros do usuário.](media/GER-BaselineSample-ERUserParameters.PNG "Captura de tela da caixa de diálogo Parâmetros de usuário")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Adicione uma nova linha base para formato de ER criado

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. No Painel de Ações, selecione **Linhas de base**.

    ![Botão Linhas de base na página Configurações.](media/GER-BaselineSample-OpenBaselinePage.PNG "Captura de tela do botão Linhas de base na página Configurações")

3. No Painel de Ações, selecione **Novo**.
4. Selecione o formato ER **Formato para aprender linhas de base de ER** que você criou anteriormente.
5. Selecione **Salvar**.

![Página de linhas de base de formato de relatório eletrônico.](media/GER-BaselineSample-AddBaseline.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")

A linha de base será adicionada para o formato **Formato para aprender linhas de base de ER**.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Configure uma regra de linha de base para a linha de base adicionada

1. Na página **Linhas de base no formato de relatório eletrônico**, no Painel de Ações, selecione o botão **Anexos** (o símbolo de clipe de papel.)
2. No Painel de Ações, selecione **Novo** \> **Arquivo**. Nos parâmetros de ER, o tipo de documento **Arquivo** deve ter sido selecionado anteriormente como o tipo de documento usado para armazenar arquivos de linha de base.
3. Selecione **Procurar** e o arquivo **out.Admin.xml** gerado quando você executou o formato do ER configurado antes.

    ![Página Anexos.](media/GER-BaselineSample-UploadBaselineFile.PNG "Captura de tela da página Anexos")

4. Feche a página **Anexos**.
5. Na Guia Rápida **Linhas de base**, selecione **Novo**.
6. No campo **Nome**, digite **Linha de base 1**.
7. No campo **Nome do componente de arquivo**, insira ou selecione **Saída**. Este valor indica que a linha de base configurada será comparada a um arquivo que é gerado usando o elemento de formato **Saída**.
8. No campo **Máscara de nome de arquivo**, digite **\*.xml**.

    > [!NOTE]
    > Você pode definir a máscara de nome de arquivo. Quando a máscara de nome de arquivo for definida, o registro de linha de base será usado para avaliar a saída gerada apenas quando o nome do arquivo de saída gerado atender essa máscara.

9. Se a linha de base configurada precisar ser usada somente quando o formato de ER **Formatar para aprender linhas de base de ER** for executado por usuários conectados a empresas específicas, selecione essas empresas no campo **Empresas**.
10. No campo **Linha de base**, insira ou selecione o anexo **out.Admin**.
11. Selecione **Salvar**.

![Página de linhas de base de formato de relatório eletrônico.](media/GER-BaselineSample-SetupBaselineLine.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Execute o formato de ER criado e verifique o log para analisar os resultados

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na árvore, expanda **Modelo para aprender linhas de base de ER** e selecione **Modelo para aprender linhas de base de ER\\Formato para aprender linhas de base de ER**.
3. Na Guia Rápida **Versões**, selecione **Executar**.
4. No campo **Inserir ID**, digite **1**.
5. Selecione **OK**.
6. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Logs de depuração de configuração**.

    ![Página Logs de execução de Relatórios eletrônicos.](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Captura de tela da página Logs de execução de Relatórios eletrônicos")

    > [!NOTE]
    > O log de execução contém informações sobre os resultados da comparação do arquivo gerado com a linha de base configurada. Neste exemplo, o log indica que o arquivo gerado e a linha de base são iguais.

7. Selecione **Excluir tudo**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Execute o formato de ER criado e verifique o log para analisar os resultados

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na árvore, expanda **Modelo para aprender linhas de base de ER** e selecione **Modelo para aprender linhas de base de ER\\Formato para aprender linhas de base de ER**.
3. Na Guia Rápida **Versões**, selecione **Executar**.
4. No campo **Inserir ID**, digite **2**.
5. Selecione **OK**.
6. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Logs de depuração de configuração**.

    ![Página Logs de execução de Relatórios eletrônicos.](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Captura de tela da página Logs de execução de Relatórios eletrônicos")

    > [!NOTE]
    > O log de execução contém informações sobre os resultados da comparação do arquivo gerado com a linha de base configurada. Neste exemplo, o log indica que o arquivo gerado e a linha de base são diferentes.

7. Selecione **Comparar**.

> [!NOTE]
> O arquivo gerado e o arquivo de linha de base são oferecidos como arquivo zip. Você pode usar ferramentas de comparação externas, como WinDiff, para comparar os arquivos e analisar as diferenças.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar a estrutura de ER (Relatórios eletrônicos)](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]