---
title: Tutorial sobre a Regression Suite Automation Tool
description: Esse artigo mostra como usar a Regression Suite Automation Tool (RSAT). Descreve diversos recursos e oferece exemplos que usam o script avançado.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 04c7d7081ece4e077881092534ed061fe2d0e999
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854589"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Tutorial sobre a Regression Suite Automation Tool

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Usa as ferramentas do navegador da internet para fazer download e salvar esta página no formato pdf.

Este tutorial aborda alguns dos recursos avançados da Regression Suite Automation Tool (RSAT), inclui uma atribuição de demonstração e descreve a estratégia e os principais pontos de aprendizagem.

## <a name="notable-features-of-rsat-and-task-recorder"></a>Recursos notáveis do RSAT e Gravador de tarefas

### <a name="validate-a-field-value"></a>Validar um valor do campo

O RSAT permite incluir etapas de validação no caso de teste para validar os valores esperados. Para obter informações sobre esse recurso, consulte o artigo [Validar valores esperados](rsat-validate-expected.md).

O exemplo a seguir mostra como é possível usar este recurso para validar se o estoque disponível é maior que 0 (zero).

1. Nos dados de demonstração da empresa **USMF**, crie uma gravação de tarefas que tenha as seguintes etapas:

    1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
    2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre um valor de **1000** para o campo **Número do item**.
    3. Selecione **Estoque disponível**.
    4. Use o Filtro Rápido para localizar registros. Por exemplo, filtro em um valor **1** para o campo **Local**.
    5. Na lista, marque a linha selecionada.
    6. Valide se o valor do campo **Total disponível** é **411.0000000000000000**.

2. Salve a gravação de tarefas como uma **gravação do desenvolvedor** e anexe-a ao caso de teste no Azure DevOps.
3. Adicione o caso de teste ao plano de teste e carregue o caso de teste no RSAT.
4. Abra o arquivo de parâmetros do Excel e Acesse a guia **TestCaseSteps**.
5. Para validar se o estoque disponível sempre será maior do que **0**, Acesse a etapa **Validar total disponível** e altere seu valor de **411** para **0**. Altere o valor do campo **Operador** de um sinal de igualdade (**=**) para um sinal de maior que (**\>**).
6. Salve e feche o arquivo de parâmetro do Excel.
7. Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel para o Azure DevOps.

Agora, se o valor do campo **Total Disponível** para o item especificado no estoque for maior que 0 (zero), os testes serão aprovados, independentemente do valor do estoque disponível real.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Variáveis salvas e encadeamento de casos de teste

Um dos principais recursos de RSAT é o encadeamento dos casos de teste, ou seja, a possibilidade de um teste passar variáveis para outros testes. Para obter mais informações, consulte o artigo [Copiar variáveis para casos de teste de encadeamento](rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Caso de teste derivado

O RSAT permite usar a mesma gravação de tarefas com vários casos de teste, permitindo que uma tarefa seja executada com configurações de dados diferentes. Consulte o artigo [Casos de teste derivados](rsat-derived-test-cases.md) para obter mais informações.

### <a name="validate-notifications-and-messages"></a>Validar notificações e mensagens

Esse recurso pode ser usado para validar se uma ação ocorreu. Por exemplo, quando uma ordem de produção é criada, prevista e iniciada, o aplicativo mostra a mensagem "Produção - Início" para notificar que a ordem de produção foi iniciada.

![Produção - Iniciar notificação.](./media/use_rsa_tool_05.png)

Você pode validar essa mensagem através do RSAT inserindo o texto da mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel para o registro apropriado.

![Guia Validação da Mensagem.](./media/use_rsa_tool_06.png)

Depois que o caso de teste for executado, a mensagem no arquivo de parâmetros do Excel será comparada à mensagem mostrada. Se as mensagens não forem correspondentes, o caso de teste falhará.

> [!NOTE]
> Você pode inserir mais de uma mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel. As mensagens também podem ser de erro ou de advertência, em vez de mensagens informativas.

### <a name="snapshot"></a>Instantâneo

Esse recurso faz capturas de tela das etapas executadas durante a gravação de tarefas. É útil para fins de auditoria ou depuração.

- Para usar este recurso ao executar o RSAT com a interface do usuário, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor do seguinte elemento de **false** para **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- Para usar este recurso durante a execução do RSAT pela CLI (por exemplo, Azure DevOps), abra o arquivo **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor do seguinte elemento de **false** para **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Quando você executa casos de teste, o RSAT gera instantâneos (imagens) das etapas e os salva na pasta de reprodução dos casos de teste no diretório de trabalho. Na pasta de reprodução, uma subpasta separada é criada com o nome **StepSnapshots**. Essa pasta contém os instantâneos dos casos de teste que são executados.

## <a name="assignment"></a>Atribuição

### <a name="scenario"></a>Cenário

1. O designer de produtos cria um novo produto liberado.
2. O gerente de produção inicia uma ordem de produção para deixar o nível de estoque com duas peças.
3. A fabricação inicia e termina a ordem de produção e verifica se a quantidade disponível está com duas peças.
4. A equipe de venda recebe um pedido de quatro peças do novo produto. Portanto, a equipe de vendas atualiza os requisitos líquidos através do plano dinâmico. Como nenhuma capacidade adicional está disponível, a política de ordem padrão é definida como "comprar em vez de fazer". Portanto, uma ordem de compra planejada é criada.
5. O comprador adiciona um fornecedor, firma a ordem de compra planejada e confirma a ordem de compra.
6. Quando as mercadorias que foram compradas chegam na loja, o operador da loja pesquisa a ordem de compra relacionada e recebe as mercadorias. Como a ordem agora está concluída, as mercadorias podem ser separadas e embaladas conforme a ordem de venda.
7. O financeiro lança a fatura de compras e a fatura de vendas.

A ilustração a seguir mostra o fluxo para esse cenário.

![Fluxo do cenário de demonstração.](./media/use_rsa_tool_14.png)

A ilustração a seguir mostra a hierarquia de processos comerciais para esse cenário no LCS Business Process Modeler.

![Processos empresariais do cenário de demonstração.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Estratégia – Aprendizagem principal

### <a name="data"></a>Dados

- Verifique se você tem volumes de dados representativos (uma cópia da produção/dados de configuração dourada mais dados migrados).
- Ao gerar novos dados por meio do gravador de tarefas, cria nomes de teste que não irão entrar em conflito com os nomes existentes (por exemplo, usar um prefixo como **RSATxxx**).
- Use a restauração pontual do Azure para reexecutar testes nos ambientes que não estão na Camada 1.
- Embora você possa usar as funções **RANDOM** e **NOW** do Excel para gerar uma combinação exclusiva, o esforço é consideravelmente alto. Veja aqui um exemplo.

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Gravador de Tarefas

- Definir cenários antes de iniciar a gravação. Um projeto bem gerenciado tem cenários de teste predefinidos. Para criar um caso de teste, considere como é previsível o resultado desses cenários de teste.
- Divida as gravações, se forem executadas por diferentes funções, ou se houver tempo de espera ou um evento externo antes da próxima etapa.
- Evite selecionar valores nas listas. Em vez disso, use formatos de texto, como **PEPS**, **AudioRM** e **SiteWH**. Quando você seleciona em uma lista, a posição do valor na lista é registrada, não o valor em si. Se itens forem adicionados a essa lista, a posição do valor pode mudar. Portanto, sua gravação usará um parâmetro diferente e o restante de cenário poderá ser afetado.
- Pense sobre o comportamento de vários usuários. Por exemplo, não presuma que sua ordem de venda recém-criada será sempre selecionada automaticamente. Em vez disso, sempre use o filtro para localizar a ordem correta.
- Use a função Copiar no gravador de tarefas para salvar o nome de um produto recém-criado, de forma que ele possa ser usado em casos de teste encadeados.
- Use a função Validar no gravador de tarefas para definir pontos de verificação que detectam se as etapas foram executadas corretamente.

### <a name="rsat"></a>RSAT

- Para executar o teste em outra empresa, você pode alterar a empresa na guia **Geral** do arquivo de parâmetro do Excel. Verifique se as configurações e os dados estão disponíveis na empresa selecionada recentemente.
- Você pode alterar o usuário do teste na guia **Geral** do arquivo de parâmetros do Excel. Especifique a ID de email do usuário que executará o caso de teste. Dessa forma, o caso de teste pode ser executado usando as permissões de segurança do usuário especificado.
- Para aguardar antes de iniciar o teste, você pode definir uma pausa na guia **Geral** do arquivo de parâmetros do Excel. Esta pausa pode ser usada em um trabalho em lotes (por exemplo, se um fluxo de trabalho tiver que ser executado antes da próxima etapa ser executada).

## <a name="advanced-scripting"></a>Script avançado

### <a name="cli"></a>CLI

O RSAT pode ser chamado de uma janela do **Prompt de Comando** ou **PowerShell**.

> [!NOTE]
> Verifique se a variável de ambiente **TestRoot** está definida para o caminho de instalação de RSAT. (No Microsoft Windows, abra **Painel de Controle**, selecione **Sistema e segurança \> Sistema \> Configurações avançadas do sistema**, e **Variáveis de Ambiente**).

1. Abra uma janela do **Prompt de Comando** ou **PowerShell** como um administrador.
2. Navegue até o diretório de instalação do RSAT.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Liste todos os comandos.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Lista todos os comandos ou mostra a ajuda para um comando específico, bem como os parâmetros disponíveis.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: parâmetros opcionais

`command`: onde ``[command]`` é um dos comandos na lista anterior.

#### <a name="about"></a>sobre

Exibe a versão do RSAT instalado.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Limpa a tela.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>fazer download

Baixa os anexos (arquivos de gravação, execução e parâmetros) do caso de teste especificado no Azure DevOps no diretório de saída. Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis e usar qualquer valor da primeira coluna como um parâmetro de **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>download: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de download aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.

##### <a name="download-required-parameters"></a>baixar: parâmetros obrigatórios

+ `test_case_id`: representa a ID do caso de teste.

##### <a name="download-optional-parameters"></a>download: parâmetros opcionais

+ `output_dir`: representa o diretório de trabalho de saída. O diretório deve existir. O diretório de trabalho das configurações será usado se esse parâmetro não for especificado.

##### <a name="download-examples"></a>baixar: exemplos

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>downloadsuite

Baixa os anexos (arquivos de gravação, execução e parâmetros) de todos os casos de teste do pacote de testes especificado no Azure DevOps no diretório de saída. Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis e usar qualquer valor como um parâmetro de **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de download aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/byid`: esta opção indica que o pacote de testes desejado é identificado por sua ID do Azure DevOps em vez do nome do pacote de testes.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite: parâmetros obrigatórios

+ `test_suite_name`: representa o nome do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **não** for especificada. Esse é o nome do pacote de testes do Azure DevOps.
+ `test_suite_id`: representa a ID do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **for** especificada. Essa ID é a identificação do pacote de testes do Azure DevOps.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite: parâmetros opcionais

+ `output_dir`: representa o diretório de trabalho de saída. O diretório deve existir. O diretório de trabalho das configurações será usado se esse parâmetro não for especificado.

##### <a name="downloadsuite-examples"></a>downloadsuite: exemplos

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>editar

Permite abrir o arquivo de parâmetros no programa Excel e editá-lo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>editar: parâmetros obrigatórios

+ `excel_file`: deve conter um caminho completo para um arquivo existente do Excel.

##### <a name="edit-examples"></a>editar: exemplos

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>gerar

Gera arquivos de execução e parâmetro de teste para o caso de teste especificado no diretório de saída. Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis. Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generate: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de geração aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/dllonly`: gera somente arquivos de execução de teste. Não regenera o arquivo de parâmetros em Excel.
+ `/keepcustomexcel`: atualiza o arquivo de parâmetros existente. Também regenera os arquivos de execução.

##### <a name="generate-required-parameters"></a>gerar: parâmetros obrigatórios

+ `test_case_id`: representa a ID do caso de teste.

##### <a name="generate-optional-parameters"></a>generate: parâmetros opcionais

+ `output_dir`: representa o diretório de trabalho de saída. O diretório deve existir. O diretório de trabalho das configurações será usado se esse parâmetro não for especificado.

##### <a name="generate-examples"></a>gerar: exemplos

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

Gera um novo caso de teste (caso de teste filho) derivado do caso de teste fornecido. O novo caso de teste também é adicionado ao pacote de testes especificado. Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis e usar qualquer valor da primeira coluna como um parâmetro de **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de geração aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.

##### <a name="generatederived-required-parameters"></a>generatederived: parâmetros obrigatórios

+ `parent_test_case_id`: representa a ID do caso de teste pai.
+ `test_plan_id`: representa a ID do plano de teste.
+ `test_suite_id`: representa a ID do pacote de teste.

##### <a name="generatederived-examples"></a>generatederived: exemplos

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Gera somente arquivo de execução de teste para o caso de teste especificado. Não gera o arquivo de parâmetros em Excel. Os arquivos são gerados no diretório de saída especificado. Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis e usar qualquer valor da primeira coluna como um parâmetro de **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de geração aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: parâmetros obrigatórios

+ `test_case_id`: representa a ID do caso de teste.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly: parâmetros opcionais

+ `output_dir`: representa o diretório de trabalho de saída. O diretório deve existir. O diretório de trabalho das configurações será usado se esse parâmetro não for especificado.

##### <a name="generatetestonly-examples"></a>generatetestonly: exemplos

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Gera os arquivos de automação de teste para todos os casos de teste no pacote de testes especificado. Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis e usar qualquer valor como um parâmetro de **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de geração aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/dllonly`: gera somente arquivos de execução de teste. Não regenera o arquivo de parâmetros em Excel.
+ `/keepcustomexcel`: atualiza o arquivo de parâmetros existente. Também regenera os arquivos de execução.
+ `/byid`: esta opção indica que o pacote de testes desejado é identificado por sua ID do Azure DevOps em vez do nome do pacote de testes.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: parâmetros obrigatórios

+ `test_suite_name`: representa o nome do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **não** for especificada. Esse é o nome do pacote de testes do Azure DevOps.
+ `test_suite_id`: representa a ID do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **for** especificada. Essa ID é a identificação do pacote de testes do Azure DevOps.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite: parâmetros opcionais

+ `output_dir`: representa o diretório de trabalho de saída. O diretório deve existir. O diretório de trabalho das configurações será usado se esse parâmetro não for especificado.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: exemplos

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>ajuda

Idêntico ao comando [?](#section) .

#### <a name="list"></a>lista

Lista todos os casos de teste disponíveis no plano de teste atual.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Lista todos os planos de teste disponíveis.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Lista casos de teste para o pacote de teste especificado. Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis e usar qualquer valor da lista como um parâmetro de **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: parâmetros obrigatórios

+ `test_suite_name`: o nome do pacote desejado.

##### <a name="listtestsuite-examples"></a>listtestsuite: exemplos

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Lista casos de teste para o pacote de teste especificado.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid: parâmetros obrigatórios

+ `test_suite_id`: a ID do pacote desejado.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid: exemplos

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Lista todos os pacotes de teste disponíveis no plano de teste atual.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>reprodução

Reproduz o caso de teste associado ao arquivo de parâmetros do Excel especificado. Este comando usa arquivos de automação locais e não baixa arquivos do Azure DevOps. Não há suporte para este comando em casos de teste de comércio com PDV.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>playback: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de reprodução aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/comments[="comment"]`: forneça uma cadeia de caracteres com informações personalizadas que será incluída no campo **Comentários** nas páginas de resumo e resultado do teste para execuções de casos de teste do Azure DevOps.

##### <a name="playback-required-parameters"></a>reprodução: parâmetros obrigatórios

+ `excel_parameter_file`: o caminho completo de um arquivo de parâmetros do Excel. O arquivo precisa existir.

##### <a name="playback-examples"></a>reprodução: exemplos

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Reproduz vários casos de teste ao mesmo tempo. Os casos de teste são identificados por sua ID. Este comando baixará os arquivos do Azure DevOps. Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis e usar qualquer valor da primeira coluna como um parâmetro de **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a>playbackbyid: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de reprodução aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/comments[="comment"]`: forneça uma cadeia de caracteres com informações personalizadas que será incluída no campo **Comentários** nas páginas de resumo e resultado do teste para execuções de casos de teste do Azure DevOps.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: parâmetros obrigatórios

+ `test_case_id1`: a ID de um caso de teste.
+ `test_case_id2`: a ID de um caso de teste.
+ `test_case_idN`: a ID de um caso de teste.

##### <a name="playbackbyid-examples"></a>playbackbyid: exemplos

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Reproduz vários casos de teste ao mesmo tempo. Os casos de teste são identificados pelos arquivos de parâmetros do Excel. Este comando usa arquivos de automação locais e não baixa arquivos do Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a>playbackmany: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de reprodução aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/comments[="comment"]`: forneça uma cadeia de caracteres com informações personalizadas que será incluída no campo **Comentários** nas páginas de resumo e resultado do teste para execuções de casos de teste do Azure DevOps.

##### <a name="playbackmany-required-parameters"></a>playbackmany: parâmetros obrigatórios

+ `excel_parameter_file1`: o caminho completo do arquivo de parâmetros do Excel. O arquivo precisa existir.
+ `excel_parameter_file2`: o caminho completo do arquivo de parâmetros do Excel. O arquivo precisa existir.
+ `excel_parameter_fileN`: o caminho completo do arquivo de parâmetros do Excel. O arquivo precisa existir.

##### <a name="playbackmany-examples"></a>playbackmany: exemplos

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Reproduz todos os casos de teste de um ou mais pacotes de teste especificados. Se a opção /local for especificada, os anexos locais serão usados para a reprodução. Caso contrário, os anexos serão baixados do Azure DevOps. Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis e usar qualquer valor da primeira coluna como um parâmetro de **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite: opções alternativas

+ `/updatedriver`: se essa opção for especificada, o WebDriver do navegador da Internet será atualizado conforme necessário antes da execução do processo de reprodução.
+ `/local`: essa opção indica que os anexos locais devem ser usados para reprodução em vez do download de arquivos do Azure DevOps.
+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de reprodução aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/comments[="comment"]`: forneça uma cadeia de caracteres com informações personalizadas que será incluída no campo **Comentários** nas páginas de resumo e resultado do teste para execuções de casos de teste do Azure DevOps.
+ `/byid`: esta opção indica que o pacote de testes desejado é identificado por sua ID do Azure DevOps em vez do nome do pacote de testes.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: parâmetros obrigatórios

+ `test_suite_name1`: representa o nome do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **não** for especificada. Esse é o nome do pacote de testes do Azure DevOps.
+ `test_suite_nameN`: representa o nome do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **não** for especificada. Esse é o nome do pacote de testes do Azure DevOps.
+ `test_suite_id1`: representa a ID do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **for** especificada. Essa ID é a identificação do pacote de testes do Azure DevOps.
+ `test_suite_idN`: representa a ID do pacote de teste. Esse parâmetro será obrigatório se a opção /byid **for** especificada. Essa ID é a identificação do pacote de testes do Azure DevOps.

##### <a name="playbacksuite-examples"></a>playbacksuite: exemplos

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

Executa todos os casos de teste do pacote de testes do Azure DevOps especificado.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>playbacksuitebyid: opções alternativas

+ `/retry[=seconds]`: se essa opção for especificada e os casos de teste forem bloqueados por outras instâncias de RSAT, o processo de reprodução aguardará o número de segundos especificado e, em seguida, tentará mais uma vez. O valor padrão para \[seconds\] é 120 segundos. Sem essa opção, o processo será cancelado imediatamente se os casos de teste forem bloqueados.
+ `/comments[="comment"]`: forneça uma cadeia de caracteres com informações personalizadas que será incluída no campo **Comentários** nas páginas de resumo e resultado do teste para execuções de casos de teste do Azure DevOps.
+ `/byid`: esta opção indica que o pacote de testes desejado é identificado por sua ID do Azure DevOps em vez do nome do pacote de testes.

##### <a name="playbacksuitebyid-required-parameters"></a>playbacksuitebyid: parâmetros obrigatórios

+ `test_suite_id`: representa a ID do pacote de testes existente no Azure DevOps.

##### <a name="playbacksuitebyid-examples"></a>playbacksuitebyid: exemplos

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>encerrar

Fecha o aplicativo. Este comando é útil somente quando os aplicativos estão sendo executados no modo interativo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>quit: exemplos

`quit`

#### <a name="upload"></a>carregar

Carrega os arquivos de anexos (arquivos de registro, execução e parâmetro), que pertencem a um pacote de testes ou a casos de teste especificados, para o Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>carregar: parâmetros obrigatórios

+ `test_suite_name`: todos os arquivos que pertencerem ao pacote de teste especificado serão carregados.
+ `test_case_id1`: representa a ID do primeiro caso de teste que deve ser carregado. Use este parâmetro somente quando nenhum nome de pacote de testes tiver sido fornecido.
+ `test_case_idN`: representa a ID do último caso de teste que deve ser carregado. Use este parâmetro somente quando nenhum nome de pacote de testes tiver sido fornecido.

##### <a name="upload-examples"></a>carregar: exemplos

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Carrega apenas o arquivo de gravação que pertence a um ou mais casos de teste especificados para o Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: parâmetros obrigatórios

+ `test_case_id1`: representa a ID do primeiro caso de teste da gravação que deve ser carregado para o Azure DevOps.
+ `test_case_idN`: representa a ID do último caso de teste da gravação que deve ser carregado para o Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording: exemplos

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>uso

Exibe os três modos de uso desse aplicativo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Ao executar o aplicativo de forma interativa:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Ao executar o aplicativo especificando um comando:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Ao executar o aplicativo fornecendo um arquivo de configurações:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Exemplos de Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Executar um caso de teste em um loop

Você tem um script de teste que cria um novo cliente. Através do script, este caso de teste pode ser executado em um loop, randomizando os seguintes dados antes de cada iteração ser executada:

- ID do cliente
- Nome do Cliente
- Endereço do cliente

O ID do cliente estará no formato *ATCUS\<number\>*, onde \<number\> é um valor entre **000000001** e **999999999**.

O seguinte exemplo usa um parâmetro, **iniciar**, para definir o primeiro número usado. Usa um segundo parâmetro, **nr**, para definir o número de clientes que deve ser criado. Para cada iteração, os parâmetros no arquivo de parâmetros do Excel são alterados usando uma função UpdateCustomer. Em seguida, a linha de comandos de RSAT é chamada em uma função de RunTestCase.

Abra o Ambiente de Script Integrado (ISE) do Microsoft Windows PowerShell no modo de administração e cole o seguinte código na janela que é nomeada **Untitled1.ps1**.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Execute um script que dependa de dados no Microsoft Dynamics 365

O exemplo a seguir usa uma chamada do Protocolo Open Data (OData) para localizar o status da ordem de uma ordem de compra. Se o status não for **faturado**, você pode, por exemplo, chamar um caso de teste RSAT que lança a fatura.

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
