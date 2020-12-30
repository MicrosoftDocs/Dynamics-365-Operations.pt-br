---
title: Automatize testes com relatórios eletrônicos
description: Este tópico explica como você pode usar o recurso de linha de base da estrutura de relatório eletrônico (ER) para automatizar os testes de funcionalidades.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0a2586afd56eef0f953454ad246ff3647a5b09d1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681439"
---
# <a name="automate-testing-with-electronic-reporting"></a>Automatizar testes com Relatório eletrônico

[!include[banner](../includes/banner.md)]

Este tópico explica como você pode usar a estrutura de relatório eletrônico (ER) para automatizar os testes de algumas funcionalidades. O exemplo neste tópico mostra como automatizar os testes de processamento de pagamentos de fornecedor.

O aplicativo usa a estrutura de ER para gerar arquivos de pagamento e os documentos correspondentes durante o processamento de pagamentos de fornecedor. A estrutura ER consiste em um modelo de dados, mapeamentos de modelo e componentes de formato que dão suporte ao processamento de pagamentos de diferentes tipos de pagamento e à geração de documentos em diversos formatos. Esses componentes podem ser baixados do Microsoft Dynamics Lifecycle Services (LCS) e importados para instância.

Também é possível personalizar cada componente da Microsoft e usá-lo como a base do seu próprio componente personalizado. Ao criar uma versão personalizada, você pode fazer alterações que aceitem requisitos específicos. Por exemplo, você pode ajustar o modelo de dados de ER e o mapeamento de modelo de ER para acessar dados de aplicativo específicos de cliente, ou pode alterar um formato de ER para modificar o layout de um documento gerado.

Você pode usar formatos de ER personalizados para processar arquivos de pagamento que geram pagamentos de fornecedor e também para processar relatórios de controle. O controle de versão tem suporte em componentes ER. Portanto, a Microsoft pode fornecer versões atualizadas de soluções de ER para o processamento de pagamentos de fornecedores. Você pode mesclar automaticamente a versão atualizada com o componente personalizado, trocando a base. Entretanto, você precisa testar a versão com troca de base para garantir que ela funcione conforme esperado.

Os modelos de dados do ER e os mapeamentos de modelo do ER são comuns para vários formatos do ER usados para processar pagamentos de diferentes tipos e gerar documentos de pagamento específicos de país/região. Portanto, é altamente desejável automatizar a aceitação de usuários e os testes de integração para que isso ocorra automaticamente em várias empresas. É importante também considerar o contexto de país/região de cada empresa de destino, o uso de conjuntos de dados diferentes etc.

Para obter mais informações sobre como criar uma versão personalizada de um formato baseado no formato que você recebeu de um provedor de configuração, consulte [ER Atualizar seu formato adotando uma nova versão base desse formato](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Conceitos principais

Os usuários avançados funcionais podem criar testes de aceitação e integração de usuário sem precisar gravar código-fonte.

- Use o recurso de linha de base do ER para comparar documentos gerados para cópias mestre. Para obter mais informações, consulte [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md).
- Use o Gravador de tarefas para gravar casos de teste e incluir a avaliação da linha de base. Para obter mais informações, consulte [Recursos do Gravador de tarefas](../user-interface/task-recorder.md).
- Casos de teste de grupo para cenários de teste obrigatórios. Para obter mais informações, consulte [Criar e automatizar testes de aceitação de usuário](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Use o Modelador de processo de negócios (BPM) no LCS para criar bibliotecas para testes de aceitação de usuário.
    - Use bibliotecas de teste do BPM para criar um plano de testes e conjuntos de testes no Microsoft Azure DevOps Services (Azure DevOps).

Os usuários avançados funcionais podem realizar testes de aceitação e integração de usuário.

- Use a RSAT (Regression Suite Automation Tool) para executar casos de teste do conjunto de testes desejado.
- Relate os resultados dos testes para o Azure DevOps e use esse serviço para investigar os resultados.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as tarefas neste tópico, você precisa preencher os seguintes pré-requisitos:

- Implantar uma topologia que dê suporte à automação de testes. Você precisa ter acesso à instância dessa topologia para a função de **Administrador do sistema**. Essa topologia deve conter os dados de demonstração que serão usados neste exemplo. Para obter mais informações, consulte [Implantar e usar um ambiente que dê suporte à contínua automação de compilações e testes](../perf-test/continuous-build-test-automation.md).
- Para executar automaticamente a aceitação de usuário e testes de integração, você deve instalar o RSAT topologia que está usando e configurá-lo da forma apropriada. Para obter informações sobre como instalar e configurar o RSAT para trabalhar com aplicativos do Finance and Operations e Azure DevOps, consulte [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Preste atenção nos pré-requisitos para usar a ferramenta. A ilustração a seguir mostra um exemplo das configurações do RSAT. O retângulo azul inclui os parâmetros que especificam o acesso ao Azure DevOps. O retângulo verde inclui os parâmetros que especificam o acesso à instância.

    ![Configurações de RSAT](media/GER-Configure.png "Captura de tela da caixa de diálogo Configurações do RSAT")

- Para organizar casos de teste em pacotes para ajudar a garantir a sequência de execução correta, de modo que você possa coletar logs de execuções de teste para gerar mais relatórios e fazer investigações, você precisa ter acesso ao Azure DevOps, partindo da topologia implantada.
- Para concluir o exemplo neste tópico, é recomendável baixar [Uso do ER para testes do RSAT](https://go.microsoft.com/fwlink/?linkid=874684). Este arquivo zip contém as seguintes guias de tarefas:

    | Conteúdo                                           | Nome e local do arquivo |
    |---------------------------------------------------|------------------------|
    | Exemplo de gravação de tarefa para preparar dados para teste | Preparar\\Gravação.xml |
    | Gravação de tarefa de exemplo para processar pagamento de fornecedor   | Processar\\Gravação.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>Prepare o módulo Contas a pagar para processar pagamentos de fornecedor

1. Entre na sua instância.
2. Baixe as configurações de ER a seguir do LCS. Para obter instruções, consulte [ER Importar uma configuração do Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md).

    - **Modelo de pagamento** Configuração de modelo de ER
    - **Mapeamento de modelo de pagamento 1611** Configuração de mapeamento de modelo de ER
    - **BACS (Reino Unido)** ER Configuração de formato

    ![Configurações de Relatórios eletrônicos](media/GER-Configurations.png "Captura de tela da página Configurações em Relatórios eletrônicos")

3. Selecione a empresa de dados de demonstração **GBSI**, que tem um contexto de país/região na Grã Bretanha.
4. Configure parâmetros de Contas a pagar:

    1. Vá para **Contas a pagar \> Configuração de pagamento \> Métodos de pagamento**.
    2. Selecione o método de pagamento **Eletrônico"**.
    3. Configure o método de pagamento para que ele use o formato de ER **BACS (REINO UNIDO)** baixado anteriormente para o processamento de pagamento do fornecedor:

        1. Na Guia Rápida **Formatos de arquivo**, defina a opção **Formato de exportação eletrônico genérico** como **Sim**.
        2. No campo **Exportar configuração de formato**, selecione **BACS (Reino Unido)**.

    ![Página Formas de pagamento](media/GER-APParameters.png "Captura de tela da página Formas de pagamento")

    > [!NOTE]
    > Se a versão tiver derivado deste formato de ER criado para dar suporte a personalizações, você poderá selecionar esta configuração no método de pagamento **Eletrônico**.

5. Crie um pagamento de fornecedor de exemplo:

    1. Vá para **Contas a pagar \> Pagamentos \> Diário de pagamentos**.
    2. Verifique se você não lançou o diário de pagamento.

        ![Página Diário de pagamentos](media/GER-APJournal.png "Captura de tela da página Diário de pagamentos")

    3. Selecione **Linhas** e insira uma linha com as informações a seguir.

        | Campo               | Exemplo de valor   |
        |---------------------|-----------------|
        | Nome do Fornecedor         | GB\_SI\_000001  |
        | Débito               | 1,000.00        |
        | Moeda            | GBP             |
        | Tipo de contrapartida | Banco            |
        | Contrapartida      | GBSI OPER       |
        | Forma de pagamento   | Eletrônico      |

    ![Página Pagamentos de fornecedor](media/GER-APJournalLines.png "Captura de tela da página Pagamentos de fornecedor")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Preparar a estrutura de ER para testar o processamento de pagamento do fornecedor

### <a name="configure-er-parameters"></a>Configurar parâmetros de ER

1. Vá para **Administração da organização \> Relatório eletrônico \> Parâmetros de relatório eletrônico**.
2. Na guia **Anexos**, no campo **Linha de base**, selecione **Arquivo** como o tipo de documento que a estrutura DM (gerenciamento de documentos) usa para manter documentos relacionados ao recurso da linha de base como anexos de DM.

    ![Página de parâmetros de relatórios eletrônicos](media/GER-ERParameters.png "Captura de tela da página Parâmetros de Relatórios eletrônicos")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>Gerar cópias de linha de base de documentos relativos a pagamentos de fornecedor

1. Vá para **Contas a pagar \> Pagamentos \> Diário de pagamentos**.
2. Selecione **Linhas**.
3. Selecione **Gerar pagamentos**.
4. Selecione o método de pagamento **Eletrônico"**.
5. Selecione a conta bancária **GBSI OPER**.
6. Defina a opção **Imprimir relatório de controle** como **Sim**.
7. Baixe a saída gerada como um arquivo de zip.
8. Abra o arquivo baixado.
9. Extraia os seguintes arquivos do arquivo baixado:

    - **Arquivo** arquivo de pagamento no formato de texto
    - **ERVendOutPaymControlReport** arquivo de relatório de controle no formato XLSX

    ![Arquivos extraídos](media/GER-APJournalProcessed.png "Captura de tela de nomes de arquivos extraídos no Windows Explorer")

### <a name="turn-on-the-er-baseline-feature"></a>Ative o recurso de linha de base do ER

1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
2. No Painel de Ações, na guia **Configurações**, selecione **Parâmetros de usuário**.
3. Defina a opção **Executar no modo de depuração** como **Sim**.

Ao ativar o parâmetro **Executar no modo de depuração**, você força a estrutura de ER a executar as seguintes ações após a execução de qualquer formato de ER que gere documentos de saída:

1. Determine se uma linha de base foi configurada para componentes do formato de ER executado.
2. Determine se cada linha de base configurada é aplicável nas condições atuais (código da empresa conectada, nome do arquivo e extensão do nome do arquivo da saída gerada etc.)
3. Para cada linha de base aplicável, execute as seguintes ações:

    1. Compare a saída gerada durante a execução do formato de ER com a linha de base correspondente.
    2. Armazene os resultados da comparação no log de depuração de configurações de ER.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>Configure as linhas de base de ER para o processamento de pagamentos de fornecedor

1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Selecione **Linhas de base**.
3. Selecione **Novo**.
4. No campo **Referência**, selecione o formato **BACS (Reino Unido)**.
5. Selecione **Anexos**.
6. Adicione uma nova linha de base para o arquivo de pagamentos de fornecedor:

    1. Selecione **Novo**.
    2. No campo **Tipo**, selecione o tipo de documento DM **Arquivo** que você configurou nos parâmetros de ER para armazenar artefatos de linha de base.
    3. Navegue para selecionar o arquivo de pagamento **Arquivo** salvo localmente no formato de texto.
    4. No campo **Descrição**, insira **Arquivo TXT de pagamento**.

7. Adicione uma nova linha de base para o relatório de controle para pagamento de fornecedores:

    1. Selecione **Novo**.
    2. No campo **Tipo**, selecione o tipo de documento DM **Arquivo** que você configurou nos parâmetros de ER para armazenar artefatos de linha de base.
    3. Navegue para selecionar o arquivo de relatório de controle **ERVendOutPaymControlReport** salvo localmente no formato XLSX.
    4. No campo **Descrição**, insira **Relatório de controle XLSX de pagamento**.

    ![Linhas de base para o arquivo de pagamento de fornecedor e relatório de controle](media/GER-BaselineAttachments.png "Captura de tela da página Configurações com o relatório Controle XLSX de Pagamentos selecionado")

8. Feche a página.
9. Na Guia Rápida **Linhas de base**, selecione **Novo** para configurar uma linha de base para o arquivo de pagamento:

    1. Nomeie a linha como **Configuração de linha de base para o arquivo de pagamento**.
    2. No campo **Nome do componente de arquivo**, selecione **arquivo** para aplicar esta linha de base à saída do formato de ER que gera o arquivo de pagamento no formato de texto BACS (Reino Unido).
    3. No campo **Empresas**, selecione **GBSI** para aplicar esta linha de base quando o formato **BACS (REINO UNIDO)** ER for executado na empresa GBSI.
    4. No campo **Máscara de nome de arquivo**, insira **\*.TXT** para aplicar esta linha de base apenas a saídas do componente do formato **arquivo** com a extensão de nome de arquivo **.txt**.
    5. No campo **Linha de base**, selecione **Arquivo TXT de pagamento** para que essa linha de base seja usada para comparação com a saída gerada.

10. Selecione **Novo** para configurar uma linha de base para o relatório de controle:

    1. Nomeie a linha como **Configuração de linha de base para o relatório de controle**.
    2. No campo **Nome do componente de arquivo**, selecione **ERVendOutPaymControlReport** para aplicar esta linha de base à saída do formato de ER que gera o relatório de controle.
    3. No campo **Empresas**, selecione **GBSI** para aplicar esta linha de base quando o formato **BACS (REINO UNIDO)** ER for executado na empresa GBSI.
    4. No campo **Máscara de nome de arquivo**, insira **\*.XLSX** para aplicar esta linha de base apenas a saídas do componente do formato **ERVendOutPaymControlReport** com a extensão de nome de arquivo **.xslx**.
    5. No campo **Linha de base**, selecione **Relatório de controle XLSX de pagamento** para que essa linha de base seja usada para comparação com a saída gerada.

    ![Guia Rápida Linhas de base na página Configurações](media/GER-BaselineRules.png "Captura de tela da Guia Rápida Linhas de base na página Configurações")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Testes de registro para validar o processamento de pagamentos de fornecedor

Como um usuário avançado funcional, você pode registrar suas próprias etapas para testar o processamento de pagamentos de fornecedor. Recomendamos que você execute (e edite, conforme necessário), a gravação de tarefas **Preparar\\Gravação.xml** baixadas anteriormente. Este registro é usado para definir todos os dados de testes para o estado correto. Esta etapa é necessária porque os testes podem ser realizados muitas vezes. Cada teste deve usar dados que estejam no mesmo estado.

### <a name="reset-user-settings"></a>Redefina configurações do usuário

1. Abra o painel padrão.
2. Selecione o botão **Configurações** (o símbolo de engrenagem).
3. Selecione **Opções de usuário**.
4. Selecione **Dados de utilização**.
5. Selecione **Redefinir**.
6. Selecione **Sim** para confirmar que você deseja redefinir dados de uso.
7. Feche a página.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>Registre as etapas para preparar dados para teste

1. Selecione o botão **Configurações** (o símbolo de engrenagem).
2. Selecione **Gravador de tarefas**.
3. Selecione **Reproduzir gravação**.
4. Selecione **Abrir neste computador**.
5. Selecione **Procurar** e selecione o arquivo salvo localmente **Preparar\\Gravação.xml**.
6. Selecione **Iniciar**.
7. Selecione **Reproduzir próxima etapa pendente** até que todas as etapas sejam executadas na gravação.

Esta gravação de tarefas executa as seguintes ações:

1. Definir o status da linha de pagamento processada como **Não**.

    ![Etapas de 3 a 4 da Gravação de tarefas](media/GER-Recording1Review1.png "Captura de tela das etapas 3 a 4 da gravação de tarefas")

2. Ative o parâmetro de usuário ER **Executar no modo de depuração**.

    ![Etapas de 9 a 10 da Gravação de tarefas](media/GER-Recording1Review2.png "Captura de tela das etapas 9 a 10 da gravação de tarefas")

3. Limpar o log de depuração de ER que contém os resultados da comparação de arquivos gerados para linhas de base.

    ![Etapas de 13 a 15 da Gravação de tarefas](media/GER-Recording1Review3.png "Captura de tela das etapas 13 a 15 da gravação de tarefas")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Grave as etapas para testar o processamento de pagamentos de fornecedor

Recomendamos que você execute (e edite, conforme necessário), a gravação de tarefas **Processar\\Gravação.xml** baixadas anteriormente. Este registro é usado para processar pagamentos de fornecedor e validar os resultados da comparação de documentos gerados para linhas de base correspondentes.

1. Selecione o botão **Configurações** (o símbolo de engrenagem).
2. Selecione **Gravador de tarefas**.
3. Selecione **Reproduzir gravação**.
4. Selecione **Abrir neste computador**.
5. Selecione **Procurar** e selecione o arquivo salvo localmente **Processar\\Gravação.xml**.
6. Selecione **Iniciar**.
7. Selecione **Reproduzir próxima etapa pendente** até que todas as etapas sejam executadas na gravação.

Esta gravação de tarefas executa as seguintes ações:

1. Comece o processamento de pagamentos de fornecedor.
2. Selecione os parâmetros de tempo de execução corretos. Ative a geração de um relatório de controle.

    ![Etapas de 3 a 8 da Gravação de tarefas](media/GER-Recording2Review1.png "Captura de tela das etapas 3 a 8 da gravação de tarefas")

3. Acesse o log de depuração de ER para registrar os resultados da comparação de saídas geradas para linhas de base correspondentes.

    No log de depuração de ER, os resultados da comparação aparecem no campo **Texto gerado**. Os campos **Componente de formato** e **Caminho de formato que causou um entrada de log** se referem ao componente de arquivo para o qual a saída gerada foi comparada à linha de base.

    ![Entradas na página Logs de execução de Relatórios eletrônicos](media/GER-ERDebugLog.png "Captura de tela de entradas na página Logs de execução de Relatórios eletrônicos")

4. A comparação da saída atual à linha de base é registrada usando a opção do Gravador de tarefas **Validar** e selecionando **Valor atual**.

    ![Uso da opção Validar para comparação com o valor atual](media/GER-TRRecordValidation.png "Captura de tela do uso da opção Validar para comparação com o valor atual")

    A ilustração a seguir mostra a aparência das etapas de validação registrada na gravação de tarefas.

    ![Etapas de 13 e 15 da Gravação de tarefas](media/GER-Recording2Review2.png "Captura de tela das etapas 13 e 15 da gravação de tarefas")

## <a name="add-the-recorded-tests-to-azure-devops"></a>Adicione os testes gravados no Azure DevOps

1. Abra o ambiente do Azure DevOps.
2. Selecione o projeto que você definiu nos parâmetros de RSAT quando você [configurou a ferramenta](#prerequisites).
3. Selecione o plano de teste que você definiu nos parâmetros de RSAT quando você [configurou a ferramenta](#prerequisites).
4. Criar um novo caso de teste para o plano de teste selecionado:

    1. Nomeie o caso de teste **Preparar dados para testar o processamento de pagamento eletrônico de fornecedor**.
    2. Anexe o arquivo **Gravação.xml** da pasta **Preparar** baixado antes.

5. Criar um novo caso de teste para o plano de teste selecionado:

    1. Nomeie o caso de teste como **Teste o processamento de pagamentos de fornecedores usando o formato de ER BACS (Reino Unido)**.
    2. Anexe o arquivo **Gravação.xml** da pasta **Processar** baixado antes.

    ![Novos casos de teste para o plano de teste selecionado](media/GER-RSAT-DevOps-Tests-Passed.png "Captura de tela dos novos casos de teste para o plano de teste selecionado")

> [!NOTE]
> Preste atenção à ordem de execução correta dos testes que são adicionados.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>Prepare o RSAT para executar os testes gravados

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Carregue os testes do Azure DevOps no RSAT

1. Abra o aplicativo RSAT local na topologia atual.
2. Selecione **Carregar** para carregar no RSAT os testes que residem atualmente no Azure DevOps.

    ![Testes carregados no RSAT](media/GER-RSAT-RSAT-Tests-Loaded.png "Captura de tela dos testes carregados no RSAT")

### <a name="create-automation-and-parameters-files"></a>Crie arquivos de automação e parâmetros

1. No RSAT, selecione os testes que você carregou do Azure DevOps.
2. Selecione **Novo** para criar arquivos de automação e parâmetros do RSAT.

    ![Arquivos de automação e parâmetros RSAT criados no RSAT](media/GER-RSAT-RSAT-Tests-Initiated.png "Captura de tela dos arquivos de automação e parâmetros RSAT criados no RSAT")

### <a name="modify-the-parameters-files"></a>Modifique os arquivos de parâmetros

1. No RSAT, selecione o caso de teste **Preparar dados para testar o processamento de pagamento eletrônico de fornecedor**.
2. Selecione **Editar**.
3. Na pasta de trabalho do Microsoft Excel que é aberta, na planilha **Geral**, modifique o código da empresa para **GBSI**, pois essa empresa será usada para a execução de teste.
4. No RSAT, selecione o caso de teste **Teste o processamento de pagamentos de fornecedores usando o formato de ER BACS (Reino Unido)**.
5. Selecione **Editar**.
6. Na pasta de trabalho do Excel que é aberta, na planilha **Geral**, modifique o código da empresa para **GBSI**.
7. Na planilha **ERFormatMappingRunLogTable**, observe que as células A:3 e C:3 contêm o texto dos campos na tabela de log de depuração de ER usado para validar os resultados da comparação da saída para a linha de base. Esses textos serão usadas para avaliar os registros de log de depuração de ER criados durante a execução do teste.

    ![Planilha ERFormatMappingRunLogTable](media/GER-RSAT-RSAT-ExcelParameters.png "Captura de tela da planilha ERFormatMappingRunLogTable")

## <a name="run-the-tests-and-analyze-the-results"></a>Execute os testes e analise os resultados

### <a name="run-the-tests-in-rsat"></a>Execute os testes no RSAT

1. No RSAT, selecione os testes carregados.
2. Selecione **Executar**.

Observe que os casos de teste são executadas automaticamente no aplicativo usando um navegador da Web.

### <a name="analyze-the-results-of-test-execution"></a>Analise os resultados da execução de testes

Os resultados da execução de testes são armazenados no RSAT. Observe que os dois testes foram aprovados.

![Testes que passaram no RSAT](media/GER-RSAT-RSAT-Tests-Passed.png "Captura de tela de testes que passaram no RSAT")

Observe que os resultados da execução de testes são enviados para o Azure DevOps para sua análise.

![Resultados da execução de teste no Azure DevOps](media/GER-RSAT-DevOps-Tests-Added.png "Captura de tela dos resultados de execução de teste no Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>Simule uma situação em que os testes falhem

Este grupo de testes deve falhar quando pelo menos uma saída gerada não coincide com a linha de base correspondente. Para obter essa situação, você pode usar sua versão derivada do formato **BACS (REINO UNIDO)** que gerará um arquivo de pagamento com conteúdo diferente da linha de base correspondente. Para simular essa situação, você pode usar o mesmo formato **BACS (REINO UNIDO)** e alterar o valor do pagamento na linha de pagamento processado.

1. Abra o aplicativo e vá para **Contas a pagar \> Pagamentos \> Diário de pagamentos**.
2. Selecione **Linhas**.
3. Selecione a linha de pagamento e, depois, **Status do pagamento \> Não**.
4. No campo **Débito**, altere o valor de **1.000,00** para **2.000,00**.
5. Selecione **Salvar** para salvar as alterações.

### <a name="run-the-tests-in-rsat"></a>Execute os testes no RSAT

1. No RSAT, selecione os testes carregados.
2. Selecione **Executar**.

Observe que os casos de teste são executadas automaticamente no aplicativo usando um navegador da Web.

### <a name="analyze-the-results-of-test-execution"></a>Analise os resultados da execução de testes

Os resultados da execução de testes são armazenados no RSAT. Observe que o segundo teste falhou durante a segunda execução.

![Resultados de teste com falha no RSAT](media/GER-RSAT-RSAT-Tests-Failed.png "Captura de tela dos resultados de teste que falharam no RSAT")

Observe que os resultados da execução de testes são enviados para o Azure DevOps para sua análise.

![Resultados de teste com falha no Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed.png "Captura de tela dos resultados de teste que falharam no Azure DevOps")

Você pode acessar o status de cada teste. Você também pode acessar o log de execução para analisar as razões de qualquer falha. Nesta ilustração, o log de execução que mostra que a falha ocorreu devido à diferença no conteúdo entre o arquivo de pagamento gerado e sua linha de base.

![Log de execução para análise de falha no Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Captura de tela de log de execução para análise de falha no Azure DevOps")

Portanto, como observou, o funcionamento de qualquer formato de ER pode ser avaliado automaticamente por meio do RSAT como a plataforma de teste e com o uso de casos de teste baseados no Gravador de tarefas que usa o recurso de linha de base de ER.

## <a name="additional-resources"></a>Recursos adicionais

- [Recursos do Gravador de tarefas](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Criar e automatizar testes de aceitação de usuário](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [Implantar e usar um ambiente que ofereçam suporte à contínua automação de compilações e testes](../perf-test/continuous-build-test-automation.md)
- [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md)
- [ER Atualize seu formato adotando uma nova versão com base nesse formato](tasks/er-upgrade-format.md)
- [Importação ER de uma configuração do Lifecycle Services](tasks/er-import-configuration-lifecycle-services.md)
