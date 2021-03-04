---
title: Melhorias no rastreamento dos resultados dos relatórios de ER gerados e na comparação deles com valores de linha de base
description: Este tópico fornece informações sobre como o recurso de linha base de ER foi aprimorado no Microsoft Dynamics 365 for Finance and Operations versão 10.0.3 (junho de 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 55e821b27f80383d8a8dc7a2d46f87e17c554078
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682838"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>Melhorias no rastreamento dos resultados dos relatórios de ER gerados e na comparação deles com valores de linha de base

[!include[banner](../includes/banner.md)]

Este tópico descreve o primeiro conjunto de melhorias feitas no recurso de linha de base da estrutura ER (relatório eletrônico). Essas melhorias estão disponíveis no Microsoft Dynamics 365 for Finance and Operations versão 10.0.3 (junho de 2019) e posterior.

## <a name="automate-the-setting-of-baseline-rules"></a>Automatize a configuração de regras de linha de base

O tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md) explica como configurar a estrutura de ER para coletar informações sobre definições de formato de ER e avaliar os resultados dessas execuções. O exemplo neste tópico mostra as etapas que devem ser concluídas.

Estas são algumas das etapas:

- Execute um formato de ER para gerar um arquivo de saída e armazenar o arquivo localmente.
- Adicione o arquivo armazenado localmente como um anexo da linha base que foi adicionada para um formato de ER.
- Configure a regra de linha de base para a linha de base adicionada. Essa configuração inclui as seguintes etapas:

    - Especifique um elemento de formato de ER usado para gerar um arquivo de saída.
    - Selecione o anexo relativo ao arquivo de saída gerado.

> [!NOTE]
> Essas etapas devem ser executadas manualmente, mesmo que os novos recursos de ER permitam que sejam automatizadas. Para saber mais sobre este recurso, conclua o exemplo a seguir.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Exemplo: automatize a configuração de regras de linha de base

Para concluir as etapas desse exemplo, primeiro você deve concluir as etapas do exemplo no tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md) na seção "Adicione uma nova linha base para formato de ER criado".

### <a name="review-added-baseline"></a>Examine a linha de base adicionada

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Selecione **Linhas de base**.

    > [!NOTE]
    > O botão **Linhas de base** no Painel de Ações está disponível apenas quando o parâmetro de usuário ER **Executar em modo de depuração** está ativado para a empresa atual.

A linha de base foi adicionada para o formato selecionado **Formatar para aprender linhas de base de ER**, mas as regras de linha de base não foram adicionadas ainda para esta linha de base.

![Página de linhas de base de formato de relatório eletrônico](media/GER-BaselineSample-AddBaseline2.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")

### <a name="make-a-new-baseline-rule"></a>Crie uma nova regra de linha de base

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na árvore, expanda **Modelar para aprender linhas de base de ER**.
3. Na árvore, selecione **Modelar para aprender linhas de base de ER\\Formatar para aprender linhas de base de ER**.
4. Na Guia Rápida **Versões**, selecione **Executar**.
5. No campo **Inserir Id**, digite **1**.
6. Defina a opção **Criar arquivos de linha de base** como **Sim**.
7. Selecione **OK**.
8. Selecione **Linhas de base**.

    ![Página Linhas de base de formato de relatório eletrônico](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")

    O arquivo de saída gerado foi automaticamente anexado à linha de base para do formato de ER executado. A regra de linha base foi adicionada automaticamente a esta linha de base e também contém a referência ao arquivo anexado.

9. No campo **Nome**, digite **Linha de base 1**.
10. No campo **Máscara de nome de arquivo**, insira **.xml**.
11. Selecione **Salvar**.

### <a name="run-the-format"></a>Execute o formato

Agora você está pronto para concluir as etapas restantes no exemplo do tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md), começando pela seção "Execute o formato de ER criado e verifique o log para analisar os resultados".

> [!NOTE]
> Quando você excluir a regra automaticamente adicionada na Guia Rápida **Linhas de base**, o anexo referenciado não será excluído automaticamente.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Configure a linha de base de forma que ela constantemente ignore partes alteradas da saída de ER

Quando um formato de ER foi criado para conter informações que são alteradas quando o formato é executado, deve-se exigir que o formato utilize o recurso de linha de base de ER para comparar os resultados gerados com os valores de linha de base. Por exemplo, as informações podem ser a data e a hora de processamento ou o identificador exclusivo de um documento gerado em diferentes formatos (identificador global exclusivo \[GUID\] etc.). Novos recursos de ER permitem configurar a regra de linha base de forma que ela ignore os elementos variáveis de um formato de ER quando o formato for executado visando comparar valores de linha base com os resultados da execução do formato. Para saber mais sobre este recurso, conclua o exemplo a seguir.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Exemplo: configure a linha de base de forma que ela constantemente ignore partes alteradas da saída de ER

Para concluir as etapas desse exemplo, primeiro você deve concluir as etapas no exemplo do tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md).

### <a name="modify-a-configured-er-format"></a>Modifique o formato de um ER configurado

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na árvore, expanda **Modelar para aprender linhas de base de ER**.
3. Na árvore, selecione **Modelar para aprender linhas de base de ER\\Formatar para aprender linhas de base de ER**.
4. Selecione **Designer**.
5. Na árvore, selecione **Saída\\Documento**.
6. Selecione **Adicionar**.
7. Na caixa de diálogo suspensa, na árvore, selecione **XML\\Atributo**.
8. No campo **Nome**, digite **ProcessamentoDataHora**.
9. Selecione **OK**.
10. Na guia **Mapeamento**, na árvore, selecione **Saída\\Documento\\ProcessamentoDataHora**.
11. Selecione **Editar fórmula**.
12. No campo **Fórmula**, insira a seguinte expressão: **DATETIMEFORMAT(NOW(), "O")**
13. Selecione **Salvar** e **Testar**.
14. Selecione **Testar** novamente para repetir o teste da expressão configurada.

    ![Página Designer de fórmulas](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Captura de tela de página Designer de fórmulas")

    > [!NOTE]
    > A guia **Resultado de teste** mostra que a expressão configurada retorna uma data e um valor de tempo diferentes sempre que chamada.

15. Feche a página **Designer de fórmulas** e selecione **Salvar**.

    ![Página do designer de formatos](media/GER-BaselineSample-FormatMappingDesign2.PNG "Captura de tela da página Designer de formato")

16. Feche a página **Designer de formato**.

### <a name="remove-an-existing-baseline-rule"></a>Remova uma regra da linha de base existente

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Selecione **Linhas de base**.
3. Na lista de linhas de base, selecione a linha de base que está configurada no formato **Formato para aprender linhas de base de ER**.
4. Na Guia Rápida **Linhas de base**, selecione **Excluir** para remover a regra de linha base que você configurou antes.

![Página de linhas de base de formato de relatório eletrônico](media/GER-BaselineSample-AddBaseline3.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>Defina substituições para associações de formato de ER criado

1. Na página **Configurações**, na Guia Rápida **Substituições**, marque **Selecionar componentes**.
2. Na árvore de componentes de formato, expanda **Saída**, expanda **Saída\\Documento** e marque a caixa de seleção **Saída\\Documento\\ProcessamentoDataHora**.
3. Selecione **OK**.

![Página de linhas de base de formato de relatório eletrônico](media/GER-BaselineSample-AddBaseline4.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")

O componente de formato de ER selecionado foi adicionado à lista de componentes na Guia Rápida **Substituições**. Quando o formato de ER básico for executado no modo de depuração, a associação de formato para cada componentes será substituída pela associação que é exibida na coluna **Associação**. Para alterar a associação padrão de um componente listado na Guia Rápida **Substituições**, selecione **Editar**.

### <a name="make-a-new-baseline-rule"></a>Crie uma nova regra de linha de base

Siga as etapas da seção "Exemplo: automatize a configuração de regras de linha de base" apresentada antes neste tópico. Uma notificação avisa que o arquivo de saída foi gerado usando configurações de linha de base e que houve uma substituição forçada das associações de formato.

![Notificação da página Configurações](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Captura de tela da notificação na página Configurações")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>Suprima avisos sobre a substituição de associações de formato

Ao configurar parâmetros específicos de ER, você pode suprimir notificações que avisam sobre a substituição de associações de formato. Essa supressão pode ser útil quando as associações de formato são substituídas de um modo autônomo usando a Regression Suite Automation Tool. Nesse caso, o aviso pode ser considerado uma falha do caso de teste que está em execução.

1. Na página **Configurações**, no Painel de Ações, na guia **Configurações**, selecione **Parâmetros de usuário**.
2. Defina a opção **Suprimir avisos de linha de base** como **Sim** e selecione **OK**.

### <a name="review-the-generated-baseline-file"></a>Revise o arquivo de linha de base gerado.

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Selecione **Linhas de base**.
3. Selecione **Anexos**.
    > [!NOTE]
    > O arquivo gerado contém o texto de data e hora de processamento (**"#"**) da associação que foi configurada na regra de linha de base adicionada, não da associação de formato.
    
4. Feche a página **Anexos**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Execute o formato de ER criado e verifique o log para analisar os resultados

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na árvore, expanda **Modelar para aprender linhas de base de ER**.
3. Na árvore, selecione **Modelar para aprender linhas de base de ER\\Formatar para aprender linhas de base de ER**.
4. Na Guia Rápida **Versões**, selecione **Executar**.
5. No campo **Inserir Id**, digite **1**.
6. Selecione **OK**.
7. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Logs de depuração de configuração**.

O log de execução contém informações sobre os resultados da comparação do arquivo gerado com a linha de base configurada. O log indica que o arquivo gerado e a linha de base são iguais, mesmo que o formato executado contenha a associação para inserir uma data e um valor de tempo constantemente alterados no arquivo de saída.

> [!NOTE]
> Embora um arquivo de saída tenha sido gerado usando as configurações de linha base que forçam a substituição das associações de formato, você não receberá avisos sobre a substituição.

## <a name="exchange-baseline-settings-between-environments"></a>Configurações de linha base Cambial entre ambientes

### <a name="export-baseline-settings"></a>Exporte configurações de linha de base

Os novos recursos de ER permitem exportar configurações de linha de base para o formato selecionado de ER do ambiente atual e armazená-las como arquivos XML. 

Para exportar configurações de linha de base, na página **Linhas de base do formato de relatório eletrônico**, selecione **Exportar**.

### <a name="import-baseline-settings"></a>Importar configurações de linha de base

As configurações de linha base exportadas podem ser importadas em um ambiente diferente. O ambiente precisa primeiro ser importado com um formato de ER. Depois, você poderá importar as configurações de linha de base.

Para importar configurações de linha base de um arquivo XML armazenado localmente, na página **Linhas de base de formato de relatório eletrônico**, selecione **Importar** e selecione **Procurar** para selecionar o arquivo XML.

![Caixa de diálogo Importar configurações de linha de base](media/GER-BaselineSample-ImportBaseline1.PNG "Captura de tela da caixa de diálogo Importar configurações de linha de base")

Para importar configurações de linha base de um arquivo XML armazenado no Microsoft SharePoint Server, com base nas configurações atuais de gerenciamento de documentos e no tipo de documento selecionado, na página **Linhas de base do formato de relatório eletrônico**, selecione **Importar da origem**. Depois, selecione o tipo de documento e o arquivos XML. O tipo de documento necessário para acessar a pasta do SharePoint deve ser configurado com antecedência.

![Caixa de diálogo Importar da origem](media/GER-BaselineSample-ImportBaseline2.PNG "Captura de tela da caixa de diálogo Importar da origem")

> [!NOTE]
> Você pode usar o gravador de tarefas para registrar as etapas para selecionar o tipo de documento necessário e o nome de arquivo na caixa de diálogo **Importar da origem**. Assim, você pode manter configurações necessárias de linha base no SharePoint Server e automaticamente importá-las, executando uma gravação de tarefas ao realizar testes automatizados usando a Regression Suite Automation Tool.

## <a name="additional-resources"></a>Recursos adicionais

- [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md)
- [Recursos do Gravador de tarefas](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]