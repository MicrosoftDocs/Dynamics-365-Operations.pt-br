---
title: Usar o tutorial da Regression Suite Automation Tool
description: Esse tópico mostra como usar a Regression Suite Automation Tool (RSAT). Descreve diversos recursos e oferece exemplos que usam o script avançado.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: cf3ca501efb4e540994b01e651eee5b8aab4ddbc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191077"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Usa o tutorial da Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Usa as ferramentas do navegador da internet para fazer download e salvar esta página no formato pdf. 

Este tutorial aborda alguns dos recursos avançados da Regression Suite Automation Tool (RSAT), inclui uma atribuição de demonstração e descreve a estratégia e os principais pontos de aprendizagem.

## <a name="features-of-rsattask-recorder"></a>Recursos do RSAT/Gravador de tarefas

### <a name="validate-a-field-value"></a>Validar um valor do campo

Para obter informações sobre este recurso, consulte [Criar uma nova gravação de tarefas que tem uma função de Validação](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Variável salva

Para obter informações sobre este recurso, consulte [Modificar uma gravação de tarefas existente para criar uma variável salva](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Caso de teste derivado

1. Abra a Regression Suite Automation Tool (RSAT) e selecione os casos de teste que você criou em [Configurar e instalar a Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).
2. Selecione **Novo \> Criar caso de teste derivado**.

    ![Comando Criar caso de teste derivado no menu Novo](./media/use_rsa_tool_01.png)

3. Você receberá uma mensagem que determina que um caso de teste derivado será criado, para cada caso de teste selecionado no conjunto de testes atual, e que cada caso de teste derivado terá sua própria cópia do arquivo de parâmetro do Excel. Selecione **OK**.

    > [!NOTE]
    > Ao executar um caso de teste derivado, ele usa a gravação de tarefas de seu caso de teste pai e sua própria cópia do arquivo de parâmetros do Excel. Dessa forma, você pode executar o mesmo teste com diferentes parâmetros, sem ter que manter mais de uma gravação de tarefas. Um caso de teste derivado não deve fazer parte do mesmo conjunto de testes do caso de teste pai.

    ![Caixa de mensagem](./media/use_rsa_tool_02.png)

    Dois casos de teste derivados adicionais são criados e a caixa de seleção **Derivado?** é marcada para eles.

    ![Casos de teste derivados criados](./media/use_rsa_tool_03.png)

    Um caso de teste derivado é criado automaticamente no Azure DevOps. É um item filho do caso de teste **Criar um novo produto** e é marcado com uma palavra-chave especial: **RSAT:DerivedTestSteps**. Esses casos de teste são adicionados automaticamente ao plano de teste no Azure DevOps.

    ![Palavra-chave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Se, por algum motivo, os casos de teste derivados que forem criados não estiverem na ordem correta, vá para Azure DevOps e reorganize-os no conjunto de testes, de forma que o RSAT possa executá-los na ordem correta.

4. Selecione os casos de teste derivados e, em seguida, selecione **Editar** para abrir os arquivos de parâmetro do Excel correspondentes.
5. Edite esses arquivos de parâmetro do Excel da mesma forma que editou os arquivos pai. Em outras palavras, certifique-se de que o ID do produto está definido, de forma que seja gerado automaticamente. Além disso, certifique-se de que a variável salva é copiada para os campos relevantes.
6. Na guia **Geral** dos arquivos de parâmetro do Excel, atualize o valor do campo **Empresa** para **USSI**, dessa forma, os casos de teste derivados serão gerados com uma entidade legal diferente daquela do caso de teste pai. Para executar os casos de teste para um usuário específico (ou a função que está associada a um usuário específico), você pode atualizar o valor do campo **Testar Usuário**.
7. Selecione **Executar** e valide se o produto é criado na entidade legal do USMF e do USSI.

### <a name="validate-notifications"></a>Validar notificações

Esse recurso pode ser usado para validar se uma ação ocorreu. Por exemplo, quando uma ordem de produção é criada, prevista e iniciada, o aplicativo mostra a mensagem "Produção - Início" para notificar que a ordem de produção foi iniciada.

![Produção - Iniciar notificação](./media/use_rsa_tool_05.png)

Você pode validar essa mensagem através do RSAT inserindo o texto da mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel para o registro apropriado.

![Guia Validação da Mensagem](./media/use_rsa_tool_06.png)

Depois que o caso de teste for executado, a mensagem no arquivo de parâmetros do Excel será comparada à mensagem mostrada. Se as mensagens não forem correspondentes, o caso de teste falhará.

> [!NOTE]
> Você pode inserir mais de uma mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel. As mensagens também podem ser de erro ou de advertência, em vez de mensagens informativas.

### <a name="validate-values-by-using-operators"></a>Validar valores usando operadores

Nas versões anteriores do RSAT, você pode validar valores somente se um valor de controle for igual a um valor esperado. O novo recurso permite validar que uma variável não é igual a, é menor que ou é maior que um valor especificado.

- Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor no seguinte elemento de **falso** para **verdadeiro**.

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    No arquivo de parâmetro do Excel, é exibido um novo campo **Operador**.

    > [!NOTE]
    > Se estiver usando uma versão mais antiga do RSAT, você deverá gerar novos arquivos de parâmetro do Excel.

    ![Campo Operador](./media/use_rsa_tool_07.png)

O exemplo a seguir mostra como é possível usar este recurso para validar se o estoque disponível é maior que 0 (zero).

1. Nos dados de demonstração da empresa **USMF**, crie uma gravação de tarefas que tenha as seguintes etapas:

    1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
    2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre um valor de **1000** para o campo **Número do item**.
    3. Selecione **Estoque disponível**.
    4. Use o Filtro Rápido para localizar registros. Por exemplo, filtro em um valor **1** para o campo **Local**.
    5. Na lista, marque a linha selecionada.
    6. Valide se o valor do campo **Total disponível** é **411.0000000000000000**.

2. Salve a gravação de tarefas para a biblioteca BPM no LCS e sincronize-o para Azure DevOps.
3. Adicione o caso de teste ao plano de teste e carregue o caso de teste no RSAT.
4. Abra o arquivo de parâmetro do Excel. Na guia **InventOnhandItem** , você verá uma seção **Validar InventOnhandItem** que contenha um campo **Operador** .

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. Para validar se o estoque disponível sempre será maior que 0, altere o valor do campo **Valor** de **411** para **0** e o valor do campo **Operador** de um sinal de igual (**=**) para um sinal maior que (**\>**).

    ![Valores dos campos Valor e Operador alterados](./media/use_rsa_tool_09.png)

6. Salve e feche o arquivo de parâmetro do Excel.
7. Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel para o Azure DevOps.

Agora, se o valor do campo **Total Disponível** para o item especificado no estoque for maior que 0 (zero), os testes serão aprovados, independentemente do valor do estoque disponível real.

### <a name="generator-logs"></a>Logs do gerador

Este recurso cria uma pasta que contém os logs dos casos de teste que foram executados.

- Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor no seguinte elemento de **falso** para **verdadeiro**.

    ```
    <add key="LogGeneration" value="false" />
    ```

Depois que os casos de teste são executados, é possível localizar os arquivos de log em **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.

![Pasta GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> Se houver casos de teste existentes antes de você alterar o valor no arquivo .config, os logs não serão gerados para esses casos de teste até que você gere novos arquivos de execução de teste.
> 
> ![Comando Gerar Somente Arquivos de Execução de texto no menu Novo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Instantâneo

Esse recurso faz capturas de tela das etapas executadas durante a gravação de tarefas.

- Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor do seguinte elemento de **falso** para **verdadeiro**.

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Em **C:\\Usuários\\\<Nome de usuário\>\\AppData\\Roaming\\regressionTool\\playback**, uma pasta separada será criada para cada caso de teste que for executado.

![Pasta de instantâneo para um caso de teste](./media/use_rsa_tool_12.png)

Em cada uma dessas pastas, você pode localizar instantâneos das etapas executadas quando os casos de teste foram executados.

![Arquivos de instantâneo](./media/use_rsa_tool_13.png)

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

![Fluxo do cenário de demonstração](./media/use_rsa_tool_14.png)

A ilustração a seguir mostra os processos empresariais para esse cenário no RSAT.

![Processos empresariais do cenário de demonstração](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Estratégia – Aprendizagem principal

### <a name="data"></a>Dados

- Verifique se você tem volumes de dados representativos (uma cópia da produção/dados de configuração dourada mais dados migrados).
- Ao gerar novos dados por meio do gravador de tarefas, cria nomes de teste que não irão entrar em conflito com os nomes existentes (por exemplo, usar um prefixo como **RSATxxx**).
- Use a restauração pontual do Azure para reexecutar testes nos ambientes que não estão na Camada 1.
- Embora você possa usar as funções **RANDOM** e **NOW** do Excel para gerar uma combinação exclusiva, o esforço é consideravelmente alto. Veja aqui um exemplo.

    ```
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

### <a name="command-line"></a>Linha de comando

O RSAT pode ser chamado de uma janela do **Prompt de Comando**.

> [!NOTE]
> Verifique se a variável de ambiente **TestRoot** está definida para o caminho de instalação de RSAT. (No Microsoft Windows, abra **Painel de Controle**, selecione **Sistema e segurança \> Sistema \> Configurações avançadas do sistema**, e **Variáveis de Ambiente**).

1. Abra uma janela do **Prompt de Comando** como um administrador.
2. Execute a ferramenta usando o diretório de instalação.

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Liste todos os comandos.

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a>Exemplos de Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Executar um caso de teste em um loop

Você tem um script de teste que cria um novo cliente. Através do script, este caso de teste pode ser executado em um loop, randomizando os seguintes dados antes de cada iteração ser executada:

- ID do cliente
- Nome do Cliente
- Endereço do cliente

O ID do cliente ficará no formato *ATCUS\<number\>*, onde \<number\> é um valor entre **000000001** e **999999999**.

O seguinte exemplo usa um parâmetro, **iniciar**, para definir o primeiro número usado. Usa um segundo parâmetro, **nr**, para definir o número de clientes que deve ser criado. Para cada iteração, os parâmetros no arquivo de parâmetros do Excel são alterados usando uma função UpdateCustomer. Em seguida, a linha de comandos de RSAT é chamada em uma função de RunTestCase.

Abra o Ambiente de Script Integrado (ISE) do Microsoft Windows PowerShell no modo de administração e cole o seguinte código na janela que é nomeada **Untitled1.ps1**.

```
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
$excelFilename = "full path to excel file parameter file"
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

```
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
