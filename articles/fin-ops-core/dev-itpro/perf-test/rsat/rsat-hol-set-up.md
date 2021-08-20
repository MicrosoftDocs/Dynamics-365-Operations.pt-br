---
title: Tutorial Configurar e instalar a Regression Suite Automation Tool
description: Este tópico é um tutorial que mostra como configurar e instalar a Regression Suite Automation Tool (RSAT).
author: robinarh
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 9cab5d9c9daf80fe5d2a510d189e71993265aa278342d5a99666615303158f61
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742267"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Tutorial Configurar e instalar a Regression Suite Automation Tool

Este tópico é um tutorial que o ajuda a configurar e iniciar a RSAT e as ferramentas associadas usando a RSAT.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Use as ferramentas do navegador da internet para fazer download e salvar esta página no formato PDF.

## <a name="key-concepts"></a>Conceitos principais

- Compreender a instalação e configuração de pré-requisitos necessárias para várias solicitações de emprego que suportam a Regression Suite Automation Tool (RSAT).
- Entender como o recurso Gravador de tarefas, junto com o Lifecycle Services (LCS) do Microsoft Dynamics e o Microsoft Azure DevOps, permite que você crie, configure, execute, investigue e relate casos de teste.
- Capacitar usuários funcionais para registrar tarefas comerciais usando o Gravador de tarefas e, em seguida, converter as gravações de tarefas em um conjunto de testes automatizados, sem ter que gravar o código-fonte.

## <a name="before-you-begin"></a>Antes de começar

### <a name="prerequisites"></a>Pré-requisitos

- Um ambiente que execute a versão 10.0 (abril de 2019) ou posterior do Microsoft Dynamics 365 for Finance and Operations é necessário para este tutorial. Para os clientes que usam o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, a atualização da plataforma (PU20) ou posterior também é suportada.
- O usuário deve ter direitos de administrador no ambiente.
- Você deve ter acesso ao LCS e ao Azure DevOps (anteriormente chamado de Microsoft Visual Studio Team Services \[VSTS\]) do locatário do cliente.
- O usuário que está criando e gerenciando conjuntos de testes deve ter uma licença dos Planos de Teste ou do Gerenciador de Testes do Azure DevOps. As seguintes licenças também fornecerão acesso aos Planos de Teste:
    - Licença do Visual Studio Enterprise
    - Licença do Visual Studio Test Professional
    - Licença de assinante das Plataformas MSDN
- O RSAT deve ter acesso ao ambiente de teste através de um navegador da Web.
- Para gerar e editar os parâmetros de teste, você deve ter o Microsoft Excel instalado.

## <a name="configure-azure-devops"></a>Configurar o Azure DevOps

### <a name="user-eligibility"></a>Qualificação do usuário

Certifique-se de que o usuário foi criado no Azure DevOps e tem um nível de assinatura que fornecerá acesso aos Planos de Teste do Azure. Uma licença dos Planos de Teste do Azure DevOps é obrigatória somente se o usuário criar e gerenciar casos de teste (isto é, nem todos os usuários de RSAT precisam dessa licença). Para obter informações sobre os requisitos de licença, consulte [Requisitos de licença](/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Criar um novo projeto do Azure DevOps

O RSAT usa o Azure Devops para gerenciamento de conjunto de teste e de caso de teste, geração de relatórios e investigação de resultados da execução do teste.

> [!NOTE]
> Você pode usar um projeto existente do Azure DevOps. Porém, se seu projeto do Azure DevOps existente for configurado de forma que tenha um modelo personalizado, você receberá um erro "Falha de Sincronização de VSTS" quando você sincronizar os casos de teste do Modelador de processo de negócios (BPM) para o Azure DevOps (consulte a seção [Testar a sincronização do BPM para Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)). Se as práticas recomendadas a seguir forem seguidas para o modelo personalizado, você poderá sincronizar os casos de teste para o Azure DevOps. (Essas práticas recomendadas são listadas na mensagem de erro).

- Não excluir nenhum tipo de item de trabalho ou campos integrados.
- Não excluir nenhum estado de um tipo de item de trabalho.
- Não adicionar nenhum campo necessário a um tipo de item de trabalho.

![Mensagem de erro com uma lista de práticas recomendadas.](./media/setup_rsa_tool_02.png)

Caso contrário, para este tutorial, recomendamos que você crie um novo projeto do Azure DevOps. Para obter mais informações, consulte [Problemas ao sincronizar BPM usando um modelo do processo do Azure DevOps (VSTS) personalizado](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Abra a URL do Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).
2. Selecione **Criar projeto** no canto superior direito da página Azure DevOps.

    ![Botão Criar projeto.](./media/setup_rsa_tool_03.png)

3. Preencha os seguintes campos e, em seguida, selecione **Criar**:

    - **Nome do Projeto**
    - **Controle de versão** – Selecione **Controle de Versão do Team Foundation**. Observe que a opção padrão, **Git**, não é suportada.
    - **Processo do item de trabalho**

    ![Caixa de diálogo Criar novo projeto.](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Criar um token de acesso pessoal

Neste tutorial você usará o Modelador de Processo de Negócios (BPM) do LCS para criar uma biblioteca de casos de teste e sincronizar seus casos de teste com o Azure DevOps. Você precisará de um token de acesso pessoal para sincronizar o BPM com o Azure DevOps.

1. Selecione o ícone de perfil no canto superior direito da página de seu projeto do Azure DevOps e, seguida, selecione **Segurança**.

    ![Comando de segurança.](./media/setup_rsa_tool_05.png)

2. No painel esquerdo, em **Segurança**, selecione **Tokens de acesso pessoal**. Em seguida, selecione **Novo Token**.

    ![O botão Novo Token na guia Tokens de acesso pessoal nas Configurações de usuário.](./media/setup_rsa_tool_06.png)

3. Preencha os seguintes campos e, em seguida, selecione **Criar**:

    - **Organização**
    - **Vencimento (UTC)** – Selecione **Definição personalizada**, e depois use o seletor de data para selecionar a última data disponível.
    - **Escopos** – Selecione a opção **Acesso total**.

    ![Caixa de diálogo Criar um novo token de acesso pessoal.](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Faça uma anotação do token de acesso pessoal que foi criado. Você precisará mais tarde quando configurar a configuração do RSAT.

    ![Token de acesso pessoal.](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>Configurar o projeto LCS

É necessário um projeto do Lifecycle Services (LCS) para sua biblioteca de teste mestre. O Modelador de processo de negócios (BPM) de LCS é usado como a biblioteca mestre para seus casos de teste. O BPM é usado para gerenciar e distribuir bibliotecas de teste em projetos de LCS. Por exemplo, um parceiro Microsoft ou fornecedor de software independente (ISV) que cria bibliotecas de testes irá liberar casos de testes na forma de bibliotecas BPM. No BPM, os casos de teste são organizados por processo comercial. O BPM não define a ordem de execução ou frequência de aprovação de seu teste. Esses detalhes são gerenciados no Azure DevOps, conforme descrito posteriormente neste tópico.  

Para o projeto de LCS, você pode usar uma implementação do cliente existente ou um projeto do parceiro.

### <a name="update-the-lcs-language"></a>Atualizar o idioma LCS

> [!NOTE]
> Para a interface do usuário (IU) mostrar corretamente os processos empresariais, o idioma preferido de LCS deve ser definido como **Inglês (Estados Unidos)**.

1. Acesse o projeto de implementação de LCS.
2. Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito e depois **Preferência de idioma**.

    ![Atualizar preferência de idioma.](./media/setup_rsa_tool_09.png)

3. No campo **Idioma preferido** , selecione **Inglês (Estados Unidos)** e **Salvar**.

    ![Guia Preferência de idioma nas Configurações do usuário.](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Configurar o LCS para conectar-se ao projeto Azure DevOps

Se você criou um novo projeto Azure DevOps anteriormente, configure o projeto LCS para conectar-se a ele. Caso contrário, se seu projeto LCS já estiver conectado ao seu projeto Azure DevOps, você pode continuar na próxima seção.

1. Acesse o projeto de implementação de LCS.
2. Selecione o botão **Menu** e, em seguida, **Configurações do projeto**.

    ![Comando das configurações do projeto.](./media/setup_rsa_tool_11.png)

3. No painel esquerdo, selecione **Visual Studio Team Services** e **Instalar o Visual Studio Team Services**.

    ![Guia Visual Studio Team Services nas Configurações do projeto.](./media/setup_rsa_tool_12.png)

4. No campo **URL do site do Azure DevOps**, informe a URL do site do Azure DevOps. No campo **Token de acesso pessoal** , insira o token de acesso pessoal que foi criado anteriormente.

    > [!NOTE]
    > Apesar de o VSTS agora ser conhecido como Azure DevOps, para conectar o LCS ao seu projeto Azure DevOps, use a URL antiga. Por exemplo, a URL do Azure DevOps usada neste tutorial é `https://dev.azure.com/D365FOFastTrack/`. Porém, na ilustração a seguir, é inserida como `https://D365FOFastTrack.visualstudio.com/`.

    ![Etapa 1 na Instalação do Visual Studio Team Services.](./media/setup_rsa_tool_13.png)

5. Selecione **Continuar**.
6. No campo **Projeto do Visual Studio Team Services**, selecione o projeto do VSTS no site selecionado para vincular-se ao projeto do LCS. O campo **Modelo do processo** é definido como **Agile**, por padrão. Para obter um modelo personalizado, revise a orientação de prática recomendada na seção [Criar um novo projeto do Azure DevOps](#create-a-new-azure-devops-project). Em seguida, selecione **Continuar**.

    ![Etapa 2 na Instalação do Visual Studio Team Services.](./media/setup_rsa_tool_14.png)

7. Revise suas configurações e selecione **Salvar**.

    ![Etapa 3 na Instalação do Visual Studio Team Services.](./media/setup_rsa_tool_15.png)

8. Selecione **Autorizar** para autorizar o LCS a acessar o site do Azure DevOps configurado em seu nome e ativar os recursos que integram-se ao VSTS.

    ![Botão Autorizar.](./media/setup_rsa_tool_16.png)

9. Uma caixa de mensagem é exibida que informa: "Você está prestes a ser redirecionado para um site externo para autorizar o LCS a se conectar ao Visual Studio Team Services em seu nome. Deseja continuar?" Selecione **Sim**.

    ![Caixa de mensagem.](./media/setup_rsa_tool_17.png)

10. Selecione **Aceitar**.

    ![Autorizando acesso.](./media/setup_rsa_tool_18.png)

11. Se estiver autorizado como usuário, a IU deverá retornar à página de configurações do projeto LCS.

    ![Usuário autorizado.](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Criar uma nova biblioteca do BPM

1. Acesse o projeto de implementação de LCS.
2. Selecione o botão **Menu** e, em seguida, **Modelador de processo de negócios**.

    ![Comando do Modelador de processo de negócios.](./media/setup_rsa_tool_20.png)

3. Selecione **Nova biblioteca**.

    ![Botão Nova biblioteca.](./media/setup_rsa_tool_21.png)

4. No campo **Nome da biblioteca** , insira um nome e, em seguida, selecione **Criar**. Para este tutorial, nomeie a biblioteca BPM **RSAT**.

    ![Caixa de diálogo Criar nova biblioteca.](./media/setup_rsa_tool_22.png)

5. Abra a nova biblioteca do BPM **RSAT**.
6. Selecione o processo **Processo de Negócios do Exemplo Principal** e, em seguida, à direita selecione **Modo de edição**.

    ![Botão Modo de edição.](./media/setup_rsa_tool_23.png)

7. Alterar o valor dos campos **Nome** e **Descrição** para **Criar um produto**. Selecione **Salvar**.

    ![Campos Nome e Descrição.](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Ambiente

### <a name="version-requirement"></a>Requisito da versão

É necessário um ambiente de área restrita ou de teste que execute a versão 10. Para clientes que estão usando a versão 7.3, a atualização da plataforma 20 ou superior também é suportada.

> [!NOTE]
> O RSAT deve ter acesso ao seu ambiente de teste através de um navegador da Web.

### <a name="user-criteria"></a>Critérios do usuário

O usuário deve ter direitos de administrador neste ambiente.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Definir configurações de Ajuda para conectar-se ao LCS

Esta etapa é necessária para a conexão com o LCS, de forma que as gravações de tarefas possam ser salvas na biblioteca do BPM apropriada no LCS, por meio do cliente.

1. Abra o cliente.
2. Acesse **Administração do Sistema \> Configuração \> Parâmetros do sistema**.
3. Na guia **Ajuda**, no campo **Configuração de ajuda do Lifecycle Services**, selecione o projeto LCS relevante (**RSAT** para este tutorial).

    ![Campo da ajuda do Lifecycle Services na guia Ajuda.](./media/setup_rsa_tool_25.png)

    As bibliotecas de BPM são preenchidas no projeto LCS apropriado.

4. Selecione **Salvar**.
5. Pode ser necessário atualizar o navegador para ver o conteúdo da Ajuda atualizado.

    ![Notificação sobre como atualizar o navegador.](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Gravações de tarefas

> [!NOTE]
> Verifique se todas as suas gravações de tarefas começam no painel principal. Mantenha gravações individuais curtas e concentre-se em uma tarefa de negócios, como criar uma ordem de venda.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Crie uma gravação de tarefas e salve-a na biblioteca do BPM

Crie uma gravação de tarefas correspondente que você possa anexar ao processo de negócios simples que foi criado na nova biblioteca do BPM.

1. Abra o cliente.
2. No painel principal, selecione o botão **Configurações** (o símbolo de engrenagem) e, em seguida, **Gravador de Tarefas**.

    ![Selecionar o Gravador de tarefas no menu Configurações.](./media/setup_rsa_tool_27.png)

3. Selecione **Criar gravação**.

    ![Botão Criar gravação.](./media/setup_rsa_tool_28.png)

4. Preencha os campos **Nome da gravação** e **Descrição da gravação** e selecione **Iniciar**.

    ![Campos Nome da gravação e Descrição da gravação.](./media/setup_rsa_tool_29.png)

5. Registre as etapas para criar um produto. Quando terminar, selecione **Parar** para parar a gravação.

    ![Etapas para criar um produto.](./media/setup_rsa_tool_30.png)

6. Selecione **Salvar no Lifecycle Services**.

    ![Salvar a gravação de tarefas no Lifecycle Services.](./media/setup_rsa_tool_31.png)

    As informações da biblioteca são carregadas do LCS.

    ![Carregar informações da biblioteca.](./media/setup_rsa_tool_32.png)

7. Selecione a biblioteca do BPM para associar à gravação de tarefas. Para este tutorial, selecione a biblioteca **RSAT** do BPM que foi criada anteriormente e o processo de negócios **Criar um produto**. Em seguida, selecione **OK**.

    ![Associando a gravação de tarefas com uma biblioteca do BPM e um processo de negócios.](./media/setup_rsa_tool_33.png)

    É exibida uma mensagem "Lifecycle Services salvo com sucesso".

    ![Mensagem sobre gravação ao LCS bem-sucedida.](./media/setup_rsa_tool_34.png)

8. Se quiser salvar a gravação de tarefas localmente e, em seguida, fazer upload dela para o BPM através do LCS, siga estas etapas:

    1. Depois que a gravação for concluída, selecione **Salvar neste PC**.

        ![Salvar neste computador.](./media/setup_rsa_tool_35.png)

    2. Na barra de Notificação do navegador, selecione **Salvar** ou **Salvar como** para salvar o arquivo em seu computador local.

        ![Barra de notificação.](./media/setup_rsa_tool_36.png)

    3. Acesse a biblioteca **RSAT** do BPM e selecione o processo de negócios em que salvará a gravação de tarefas.
    4. Na guia **Visão geral** , selecione **Carregar**.

        ![Botão Carregar.](./media/setup_rsa_tool_37.png)

    5. Selecione **Procurar** e o arquivo .axtr salvo anteriormente. Depois, selecione **Carregar**.

        ![Selecione o arquivo .axtr para carregar.](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>Testar a sincronização do BPM para o Azure DevOps

Agora que uma gravação de tarefas está vinculada ao processo de negócios, você deve validar se o processo de negócios e a gravação de tarefas associada podem ser sincronizados ao Azure DevOps como um recurso e um caso de teste (respectivamente), usando o recurso de sincronização do VSTS no LCS.

> [!NOTE]
> O tipo de item de trabalho correspondente que é criado no Azure DevOps irá variar, dependendo do modelo do processo selecionado quando você configurou o projeto LCS com o Azure DevOps, conforme descrito na seção [Criar um novo projeto do Azure DevOps](#create-a-new-azure-devops-project).

1. Acesse a biblioteca BPM e abra a biblioteca **RSAT** criada anteriormente.
2. Selecione o botão de reticências (**...**) e depois **Sincronização de VSTS**.

    ![Comando de sincronização de VSTS no menu de reticências.](./media/setup_rsa_tool_39.png)

    Depois que a sincronização de VSTS for concluída, uma guia **Requisitos** aparecerá no lado esquerdo e incluirá o item de trabalho do Azure DevOps correspondente.

    > [!NOTE]
    > O item de trabalho criado no Azure DevOps terá o nome da biblioteca do BPM como o prefixo do título.

    ![Guia Requisitos.](./media/setup_rsa_tool_40.png)

3. Atualize a página.
4. Selecione o botão de reticências (**...**). Você verá uma opção adicional, **Sincronizar casos de teste**. Selecione esta opção.

    ![Comando Sincronizar casos de teste no menu de reticências.](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Se a opção **Sincronizar casos de teste** não estiver disponível depois que você atualizar a página, Acesse a página principal do BPM e selecione **Sincronizar casos de teste** para toda a biblioteca. Assim, você força eficientemente uma sincronização para toda a biblioteca.
    >
    > ![Selecionar Sincronizar casos de teste para toda a biblioteca.](./media/setup_rsa_tool_42.png)

    Depois que Sincronizar casos de teste for concluída, um novo caso de teste será criado na guia **Requisitos**.

    ![Novo caso de teste na guia Requisitos.](./media/setup_rsa_tool_43.png)

5. Acesse seu projeto do Azure DevOps e selecione **Quadros \> Itens de trabalho**.

    ![Comandos Itens de Trabalho nos Quadros.](./media/setup_rsa_tool_44.png)

6. Validar se existe o item de trabalho e o caso de teste que você criou através da sincronização do BPM.

    ![Item de trabalho e caso de teste.](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Instalar e Configurar o RSAT

O RSAT pode ser instalado em qualquer computador que execute o Windows 10 e que possa conectar-se ao ambiente através de um navegador da Web (Internet Explorer ou Google Chrome).

> [!NOTE]
> Antes de instalar uma nova versão de ferramenta, recomendamos que você desinstale a versão anterior.

### <a name="install-an-authentication-certificate"></a>Instalar um certificado de autenticação

Para habilitar a autenticação, você deve gerar e instalar um certificado no mesmo computador que o RSAT está sendo executado.

#### <a name="generate-a-certificate"></a>Gerar um certificado

1. Para gerar um arquivo do certificado, abra a janela do Microsoft Windows PowerShell como administrador e execute o seguinte comando.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. Abra o gerenciador de certificados inserindo **certlm.msc** na caixa de diálogo **Executar** e confirme se o **Certificado de teste automatizado D365** foi criado em **Certificados \> Pessoais**.

    > [!NOTE]
    > Certifique-se de inserir **certlm.msc**, não **certmgr.msc** porque os certificados estão armazenados no computador local.

    ![Certificado de teste automatizado D365.](./media/setup_rsa_tool_46.png)

3. Clique com o botão direito do mouse no certificado e, em seguida, selecione **Copiar**.
4. Acesse **Autoridades de certificação raiz confiáveis \> Certificados**.

    ![Pasta Certificados na pasta Autoridades de certificação raiz confiáveis.](./media/setup_rsa_tool_47.png)

5. No menu **Ação**, selecione **Colar** para copiar o certificado no local **Autoridades de certificação raiz confiáveis**.

    ![Comando Colar no menu Ação.](./media/setup_rsa_tool_48.png)

6. Para obter a impressão digital do certificado instalado, mas sem espaços ou caracteres especiais, abra a janela do Windows PowerShell como um administrador e execute os seguintes comandos.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Salve a impressão digital porque você precisará dela posteriormente quando atualizar os arquivos .wif para o Application Object Server (AOS) e defina a configuração de RSAT.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Configure o computador AOS para confiar na conexão

> [!NOTE]
> Se o ambiente for um ambiente de Camada 2+, a impressão digital do certificado deverá ser atualizada no arquivo wif.config para **todos** os computadores AOS do ambiente.

1. Estabeleça uma conexão do Remote Desktop Protocol (RDP) para o computador AOS. Os detalhes de entrada estão disponíveis na página detalhes do ambiente no LCS.
2. Abra o Microsoft Internet Information Services (IIS) e localize o **AOSService** na lista de sites.

    ![AOSService na lista de sites.](./media/setup_rsa_tool_49.png)

3. Clique com o botão direito do mouse em **Explorar** para abrir a pasta **\<Drive\>: \\AosService\\WebRoot**. Localize o arquivo **wif.config**.

    ![Arquivo Wif.config na pasta Webroot.](./media/setup_rsa_tool_50.png)

4. Atualize o arquivo **wif.config** adicionando uma nova entrada de autoridade em seu certificado e no nome da autoridade, conforme mostrado no exemplo a seguir.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Se vários usuários estiverem usando o mesmo aplicativo, cada usuário deverá gerar impressões digitais separadas e cada uma dessas impressões deverá ser adicionada à seção **\<keys\>**.

5. Se houver mais de um computador AOS, repita as etapas 3 a 4 para cada computador adicional.

    > [!NOTE]
    > Ao contrário dos ambientes da Camada 2, os novos ambientes da Camada 2 são implantados com duas instâncias do AOS.

6. Execute **iisreset** em todos os computadores AOS.

    > [!NOTE]
    > Se você não tiver direitos administrativos para executar o **iisreset** em um computador Camada 1, na página detalhes do Ambiente na LCS, selecione Manter > Reiniciar serviços.

#### <a name="tier-2-environment"></a>Ambiente da Camada 2+

Se um ambiente de Camada 2+ (área restrita ou superior do Teste de Aceitação Padrão) for usado, verifique ou defina a seguinte configuração de registro no computador onde o RSAT está instalado. Essa etapa é necessária porque ajuda a evitar erros de conexão RSAT ou de autenticação.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>Instalar RSAT

1. Acesse o <https://www.microsoft.com/download/details.aspx?id=57357> e selecione **Baixar**.
2. Selecione todos os arquivos e depois **Próximo**.

    ![Selecionando todos os arquivos.](./media/setup_rsa_tool_51.png)

3. Clique duas vezes no pacote .msi para executar o instalador. Em seguida, quando a instalação for concluída, selecione **Concluir**.

    ![Arquivo do Instalador do RSAT.](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Instalar Selenium e drivers dos navegadores

Em versões anteriores do RSAT, você teve que instalar o Selenium e os drivers do navegador. Não é mais necessário instalar esses drivers porque eles são instalados automaticamente.

1. Na primeira vez que você abrir o RSAT, será solicitado que você baixe automaticamente e instale o Selenium. Para obter mais informações, consulte a seção [Configurar RSAT](#configure-rsat).
2. Antes de executar um caso de teste, será solicitado que você baixe automaticamente e instale o driver do navegador que corresponde ao navegador padrão selecionado na configuração do RSAT. Para obter mais informações, consulte a seção [Carregar e executar casos de teste](#load-and-run-test-cases).

## <a name="get-started-with-rsat"></a>Começar a usar o RSAT

### <a name="create-a-test-plan-and-test-suites"></a>Crie um plano de teste e conjuntos de testes

1. Acesse o projeto Azure DevOps e selecione **Planos de Teste**.

    ![Comando Planos de teste.](./media/setup_rsa_tool_53.png)

2. Selecione **Novo Plano de Teste**.

    ![Botão Novo Plano de Teste.](./media/setup_rsa_tool_54.png)

3. Preencha o campo **Nome** e, em seguida, selecione **Criar**. Para este tutorial, nomeie o plano de teste como **Plano de Teste RSAT**.

    ![Caixa de diálogo Novo Plano de Teste.](./media/setup_rsa_tool_55.png)

4. Selecione o sinal de adição (**+**) e, em seguida, selecione **Conjunto estático** para criar um conjunto estático no novo plano de teste. Nomeie o novo conjunto de teste **T01 – Fabricar para Armazenar**.

    > [!NOTE]
    > Você também pode criar um pacote com base na consulta, se quiser que os novos casos de teste do BPM sejam incluídos automaticamente no conjunto de testes do RSAT.

    ![Criando um conjunto estático.](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Anexar casos de teste aos conjuntos de testes

1. Selecionar **Adicionar existente** no lado direito para adicionar os casos de teste existentes ao conjunto de testes.

    ![Botão Adicionar existente.](./media/setup_rsa_tool_57.png)

2. Na página **Adicionar casos de teste ao conjunto**, selecione **Executar consulta** e, em seguida, selecione o caso de teste para adicionar ao conjunto de testes. Para este tutorial, selecione o caso de teste **Criar um novo produto**. Em seguida, selecione **Adicionar casos de teste** no canto inferior direito da página (este botão não é mostrado na ilustração a seguir).

    ![Botão Executar consulta.](./media/setup_rsa_tool_58.png)

    O caso de teste é adicionado ao conjunto de testes **T01-Fabricar para Armazenar**.

    ![Caso de teste adicionado ao conjunto de teste.](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>Configurar RSAT

1. Abrir RSAT.

    ![Ícone de RSAT.](./media/setup_rsa_tool_60.png)

2. Você receberá uma mensagem de aviso que informa “, O Regression Suite Automation Tool requer o Selenium. Deseja baixá-lo e instalá-lo automaticamente?" Selecione **Sim**.

    ![Mensagem de aviso de que o Regression Suite Automation Tool requer o Selenium.](./media/setup_rsa_tool_61.png)

3. Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito e, em seguida, na caixa de diálogo que aparece, preencha os seguintes campos:

    - **Url do Azure DevOps** – Insira o URL do seu projeto Azure DevOps, como, por exemplo, `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Token de Acesso** – Insira o token de acesso que permite que a ferramenta conecte-se ao Azure DevOps. Use o token de acesso pessoal criado anteriormente neste tutorial. Para obter mais informações, consulte [Autenticar acesso com tokens de acesso pessoal](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Nome do Projeto** – Selecione o nome do seu projeto do Azure DevOps .
    - **Plano de Teste** – Selecione o plano de teste do Azure DevOps que contém os casos de teste. Para obter mais informações, consulte [Criar planos de teste e conjuntos de teste](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). Após selecionar um plano de teste, selecione **Conexão de Teste** para testar sua conexão ao Azure DevOps.
    - **Nome do host** – insira o nome do host do ambiente de teste, como **\<myaos\>.cloudax.dynamics.com**. Não inclua o prefixo **https://** ou **http://**.
    - **Nome do host do SOAP** – Insira o nome do host do SOAP do ambiente de teste. Geralmente, o nome do host do SOAP é igual ao nome do host, mas tem um sufixo **soap** . Veja um exemplo: **\<myaos\>soap.cloudax.dynamics.com**. Não inclua o prefixo **https://** ou **http://**.

        > [!NOTE]
        > Para localizar o nome do host e o nome do host do SOAP, abra o Gerenciador do IIS, clique com o botão direito do mouse em **Sites \> AOSService** e, em seguida, selecione **Editar associações**. Os valores da coluna **Nome do Host** fornecem o nome do host e o nome do host do SOAP (o nome do host do SOAP tem o sufixo **soap** na URL).

        ![Nome do host e nome do host do SOAP na coluna Nome do Host.](./media/setup_rsa_tool_63.png)

    - **Nome do usuário administrador** – Insira o endereço de email de um usuário administrador no ambiente de teste.
    - **Impressão digital** – Insira a impressão digital do certificado de autenticação, conforme descrito anteriormente neste tutorial.
    - **Diretório de trabalho** – Especifique o local de pasta para armazenar arquivos de automação de teste, como arquivos de dados de teste do Excel. Por exemplo, informe ou selecione **C:\\Temp\\RegressionTool**.

        > [!NOTE]
        > Se o nome da pasta tiver espaços, a execução falhará porque a pasta não poderá ser encontrada. Este é um problema conhecido e deverá ser corrigido na versão mais recente da ferramenta.

    - **Navegador padrão** – Selecione **Internet Explorer** ou **Google Chrome**. Certifique-se de que os drivers do navegador apropriados foram instalados.
    - **Testar tempo limite da execução** – Especifique o tempo limite, em minutos, para execuções de teste. Quando o tempo limite passar, todas as janelas ativas serão fechadas e os casos de teste pendentes falharão.
    - **Testar tempo limite da ação** – Este campo controla o período, em minutos, para solicitações do servidor do ambiente do Finance and Operation. Geralmente, o valor padrão (2 minutos) deve ser suficiente. Porém, para ambientes mais lentos, talvez você queira aumentar o valor, houver erros relacionados aos tempos limite.
    - **Nome da empresa** – Insira o nome da empresa a ser usada como a empresa padrão quando os arquivos de parâmetros do Excel forem criados. Você pode alterar a empresa posteriormente, editando o arquivo de parâmetros do Excel.

    ![Caixa de diálogo Configurações.](./media/setup_rsa_tool_62.png)

4. Selecione **Aplicar** para aplicar e salvar suas configurações.

    Para salvar suas configurações atuais em um arquivo de configuração em seu computador, selecione **Salvar como**. Para restaurar suas configurações de um arquivo de configuração em seu computador, selecione **Abrir**.

5. Selecione **Fechar** para fechar a caixa de diálogo.

### <a name="load-and-run-test-cases"></a>Carregar e executar casos de teste

1. Selecione **Carregar** para carregar o plano de teste **Plano de Teste de RSAT** do projeto Azure DevOps.

    ![Botão Carregar.](./media/setup_rsa_tool_64.png)

2. Selecione o caso de teste **Criar um novo produto** do conjunto de testes e selecione **Novo \> Gerar arquivos de Parâmetro e Execução de Teste**.

    ![Comando Gerar Arquivos de parâmetros e Execução de Teste no menu Novo.](./media/setup_rsa_tool_65.png)

    O arquivo de parâmetros do Excel é criado na pasta local especificada na configuração de RSAT (por exemplo, **C:\\Temp\\RegressionTool**).

    ![Arquivo de parâmetro do Excel criado.](./media/setup_rsa_tool_66.png)

3. Se quiser salvar os arquivos de parâmetro, selecione **Carregar**. Os arquivos de automação de teste de todos os casos de teste selecionados são carregados para o Azure DevOps para uso futuro. (Esses arquivos incluem os arquivos de parâmetro de teste do Excel).

    Dessa forma, você pode selecionar **Carregar** para carregar os arquivos de parâmetro (e arquivos de automação) do caso de teste diretamente do Azure DevOps. Você não precisa gerar novamente os arquivos de parâmetro. Esta abordagem se tornará importante posteriormente, quando você quiser manter as alterações no arquivo de parâmetro e não quiser que elas sejam substituídas.

4. Para verificar se os arquivos de automação e os arquivos de parâmetros foram salvos no Azure DevOps, Acesse o projeto Azure DevOps, selecione **Quadros \> Itens de trabalho** e selecione o caso de teste **Criar um novo produto**. Na guia **Anexos** , você deverá visualizar quatro arquivos:

    - **.cs** – C\# arquivo de automação
    - **.dll** – Arquivo de automação compilado como uma montagem
    - **.xlsx** – Arquivo de parâmetros do Excel
    - **.xml** – arquivo de gravação

    ![Arquivos na guia Anexos.](./media/setup_rsa_tool_67.png)

5. Selecione o caso de teste a ser executado e, em seguida, **Executar**.

    > [!NOTE]
    > Antes de executar os casos de teste, se estiver usando o Internet Explorer como o navegador, certifique-se de que a resolução da área de trabalho está definida como **100%** em **Configurações de Vídeo do Windows \> Ajustar escala e layout**. Se você não puder alterar essa configuração em uma máquina virtual (VM), altere-a no cliente (laptop) do qual você está tentando acessar a VM. As configurações da resolução serão então herdadas pelas configurações de exibição da VM.

    ![Resolução da área de trabalho definida como 100%.](./media/setup_rsa_tool_68.png)

6. Se os drivers do navegador não estiverem instalados no sistema, você receberá uma mensagem de aviso que informará, "Esta operação requer o driver do \<browser name\>. Deseja baixá-lo e instalá-lo automaticamente?" Selecione **Sim**.

    ![Mensagem de aviso do Internet Explorer.](./media/setup_rsa_tool_69.png)

    ![Mensagem de aviso do Chrome.](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Se estiver usando o Chrome como o navegador e receber uma mensagem de erro que informa que a sessão não foi criada porque a versão do Chrome não está correta, baixe o driver do Chrome mais recente do <http://chromedriver.chromium.org/downloads> para a pasta **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.

    ![Mensagem de erro do Chrome.](./media/setup_rsa_tool_71.png)

    O caso de teste é executado e o campo **Resultado** é atualizado.

    ![Campo Resultado Atualizado.](./media/setup_rsa_tool_72.png)

    Se você seguiu este tutorial como está escrito, o caso de teste **Criar um novo produto** falhará porque a gravação da tarefa para criar um produto salvou o nome do produto como um valor codificado. Se você executar novamente o mesmo caso de teste, deverá receber uma mensagem de erro, porque o produto já existe.

    ![Campo Resultado definido como Com Falha.](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Exibir os resultados do teste

1. Clique duas vezes no caso de teste com falha.

    Você receberá uma mensagem de erro.

    ![Mensagem de Erro.](./media/setup_rsa_tool_73.png)

2. Selecione **Detalhes** para exibir a mensagem de erro inteira.

    ![Mensagem de erro inteira.](./media/setup_rsa_tool_74.png)

3. Para exibir uma versão detalhada da mensagem de erro no Azure DevOps, selecione **Abrir no Azure DevOps**. No Azure DevOps, você pode exibir o status do caso de teste e a mensagem de erro detalhada.

    ![Mensagem de erro detalhada no Azure DevOps.](./media/setup_rsa_tool_75.png)

4. Para exibir os resultados de teste diretamente no projeto do Azure DevOps , Acesse **Planos de Teste \> Planos de Teste \> Execuções**. Clique duas vezes na execução do teste na qual você deseja ver mais detalhes.

    ![Lista de execuções de testes no Azure DevOps.](./media/setup_rsa_tool_76.png)

5. A guia **Resumo de execução** indica que o caso de teste falhou, mas não fornece a mensagem de erro real. Para exibir a mensagem de erro detalhada, selecione a guia **Resultados do teste**.

    ![Guia Resumo de execução.](./media/setup_rsa_tool_77.png)

    A guia **Resultados de teste** fornece informações do caso de teste, junto com o resultado a mensagem de erro.

    ![Guia Resultados do teste.](./media/setup_rsa_tool_78.png)

6. Clique duas vezes no registro relevante para exibir a mensagem de erro detalhada.

    ![Mensagem de erro detalhada.](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Todas as mensagens de erro também estão disponíveis localmente em **C:\\Usuários\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.

7. Também é possível exportar os resultados de execução do teste do nível do plano de teste, selecionando **Exportar**.

    ![Exportando um plano de teste.](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Modifique o arquivo de parâmetro do Excel

1. Abrir RSAT.
2. Selecione o caso de teste e, em seguida, selecione **Editar** para abrir o arquivo de parâmetro do Excel.

    Na folha **EcoResProductCreate**, observe que o valor do campo **Número do produto** está codificado. Você deve atualizar este campo para um novo número de produto antes de executar o caso de teste novamente.

3. Para gerar um número exclusivo de produto para cada execução sem precisar reabrir o arquivo de parâmetros do Excel e atualizar manualmente o número do produto todas as vezes, use a seguinte fórmula do Excel.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Além da guia **Geral**, o arquivo de parâmetros do Excel contém uma guia de dados para cada página do formulário que o caso de teste visita.

    ![Campo Número do produto.](./media/setup_rsa_tool_81.png)

4. Selecione **Salvar** e feche a pasta de trabalho do Excel.
5. Selecione **Carregar** para salvar o arquivo de parâmetros do Excel para o Azure DevOps.

    ![Mensagem de carregamento bem-sucedido.](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Para executar casos de teste em um contexto de usuário específico, informe o ID do e-mail do usuário no campo **Testar Usuário** na guia **Geral** do arquivo de parâmetros do Excel. Na versão mais recente do RSAT, o layout dos campos no arquivo de parâmetros do Excel foi atualizado, mas o conceito permanece o mesmo.
    >
    > ![Campo Testar Usuário.](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Validar os resultados

- Selecione **Executar** para executar novamente o caso de teste e verificar se o caso de teste foi aprovado. Você pode exibir os resultados de teste, conforme descrito na seção [Exibir os resultados de teste](#view-the-test-results).

    ![Campo Resultado definido como Aprovado.](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Encadeamento dos casos de testes

Um recurso-chave de RSAT é o encadeamento dos casos de teste (isto é, a capacidade de um teste aprovar valores para outros testes). Os casos de teste são executados de acordo com sua ordem definida no plano de teste do Azure DevOps. (Essa ordem também pode ser atualizada na própria ferramenta de teste.) Portanto, se você quiser passar variáveis de um caso de teste para outro, é muito importante que os testes estejam na ordem correta.

Nesta seção, você criará uma variável salva no primeiro caso de teste, criará um segundo caso de teste e transmitirá a variável salva do primeiro caso de teste para o segundo caso de teste. Em seguida, você executará os casos de teste como um caso de teste encadeado no RSAT.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Modificar uma gravação de tarefas existente para criar uma variável salva

1. Abra o cliente.
2. Selecione o botão **Configurações** (o símbolo da engrenagem) e depois, selecione **Gravador de tarefas**.
3. Selecione **Editar Gravação**.

    ![Botão Editar Gravação.](./media/setup_rsa_tool_85.png)

4. Selecione **Abrir do Lifecycle Services**.

    ![Botão Abrir do Lifecycle Services.](./media/setup_rsa_tool_86.png)

5. Escolha **Selecione a biblioteca Lifecycle Services**.

    ![Botão Selecione a biblioteca Lifecycle Services.](./media/setup_rsa_tool_87.png)

    As bibliotecas de BPM são carregadas do LCS.

    ![Carregar bibliotecas de BPM.](./media/setup_rsa_tool_88.png)

6. Depois que as bibliotecas de BPM forem carregadas do LCS, selecione a biblioteca **RSAT** de BPM e o processo de negócios **Criar um novo produto** que tem a gravação de tarefas associada a ele. Em seguida, selecione **OK**.

    ![Selecionando uma biblioteca de BPM e um processo de negócios.](./media/setup_rsa_tool_89.png)

7. O nome da gravação de tarefas apropriada é inserido no campo **Nome da gravação**. Selecione **Iniciar**.

    ![Nome da gravação de tarefas no campo Nome da gravação.](./media/setup_rsa_tool_90.png)

8. Acesse **Gerenciamento de informações do produto \> Produtos** e selecione **Novo** para abrir a página onde a gravação de tarefas original, **Criar um produto**, foi gravada.
9. Selecione **Inserir etapa**.

    > [!NOTE]
    > A nova etapa é inserida **depois** da etapa selecionada no painel.

    ![Botão Inserir etapa.](./media/setup_rsa_tool_91.png)

10. Clique com o botão direito do mouse no campo **Número do produto** e selecione **Gravador de tarefas \> Copiar**.

    ![Comando Copiar.](./media/setup_rsa_tool_92.png)

11. Uma nova etapa será adicionado ao painel. Anote o valor do campo **Número do produto**, porque você precisará dele posteriormente.

    ![Nova etapa adicionada.](./media/setup_rsa_tool_93.png)

12. Selecione **Edição concluída**.
13. Selecione **Salvar no Lifecycle Services** e associe a nova gravação de tarefas à mesma biblioteca de BPM e ao processo de negócios ao qual a gravação de tarefa original estava associada. Para obter mais informações, consulte a seção [Criar uma gravação de tarefas e salvá-la na biblioteca do BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Acesse a biblioteca BPM e selecione **Sincronizar casos de teste** para substituir a gravação de tarefas que está vinculada ao caso de teste no Azure DevOps, conforme descrito na seção [Testar a sincronização do BPM para o Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).
15. Abra o RSAT e selecione **Carregar** para recarregar todos os casos de teste no conjunto de testes. Você deve gerar novamente os arquivos de parâmetro e automação para o caso de teste apropriado, selecionando o caso de teste e **Novo \> Gerar Arquivos de parâmetros e Execução de Teste**, conforme descrito na seção [Carregar e executar casos de teste](#load-and-run-test-cases).

    > [!NOTE]
    > Se o arquivo de parâmetros do Excel ficou aberto, a regeneração falhará. Portanto, certifique-se de que o arquivo de parâmetros do Excel para o caso de teste está fechado antes de gerar o novo arquivo de parâmetros do Excel.

16. Selecione **Editar** para abrir o novo arquivo de parâmetros do Excel. Você verá uma nova entrada **Variável salva** na linha 9. Esta variável, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** é salva no arquivo XML de gravação de tarefas e pode ser usada nos testes subsequentes.

    ![Entrada de variável salva.](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Criar um novo caso de teste

1. Acesse biblioteca **RSAT** do BPM.
2. Selecione o processo **Processo de Negócios Suporte de Exemplo** e, em seguida, no lado direito selecione **Modo de edição**.
3. Altere o valor do campo **Nome** e **Descrição** para **Liberar um produto**. Selecione **Salvar**.

    ![Nome e descrição alterados para Liberar um produto.](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Criar uma nova gravação de tarefas que tenha a função Validar

- Criar uma gravação de tarefas para liberar o produto que foi criado anteriormente para a entidade legal USRT. Para obter mais informações, consulte a seção [Criar uma gravação de tarefas e salvá-la na biblioteca do BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > Para casos de testes encadeados, sempre recomendamos que você localize ou filtre o registro que precisa *digitando manualmente o valor do campo*. Dessa forma, a ferramenta pode determinar o registro de que a ação deve ser tomada, no caso de teste subsequente.

    ![Nova gravação de tarefas que tem uma função Validar.](./media/setup_rsa_tool_96.png)

    Como mostra a ilustração anterior, após o produto ser encontrado usando o Filtro Rápido, mas antes de selecionar **Liberar produtos**, você valida o valor do campo **Número do produto** para certificar-se de que o ID do produto é o ID do produto que foi criado anteriormente. Para validar o valor, clique com o botão direito no campo **Número do produto** e, em seguida, selecione **Gravador de tarefas \> Validar \> Valor Atual**.

    ![Validando o valor atual.](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Salve a gravação de tarefas para o BPM

1. Depois que a gravação de tarefas for concluída, selecione **Salvar no Lifecycle Services**.

    ![Salvar a gravação de tarefas concluídas no Lifecycle Services.](./media/setup_rsa_tool_98.png)

2. As informações da biblioteca são carregadas do LCS.

    ![Carregar informações da biblioteca do LCS.](./media/setup_rsa_tool_99.png)

3. Selecione a biblioteca do BPM para associar à gravação de tarefas. Para este tutorial, selecione a biblioteca **RSAT** do BPM que foi criada anteriormente e o processo de negócios **Liberar um produto**. Em seguida, selecione **OK**.

#### <a name="sync-bpm-to-azure-devops"></a>Sincronizar BPM ao Azure DevOps

1. Acesse a biblioteca BPM e abra a biblioteca **RSAT**.
2. Selecione **Sincronização de VSTS** e, em seguida, **Sincronizar casos de teste**. Para obter mais informações, consulte a seção [Testar a sincronização do BPM para o Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).

    Depois que a sincronização for concluída, o novo item de trabalho e o caso de teste correspondente para o processo de negócios **Liberar um produto** aparece no Azure DevOps em **Quadros \> Itens de Trabalho**.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Adicione o novo caso de teste ao conjunto de testes existente

1. Acesse **Planos de teste \> Planos de teste** e selecione o **Plano de Teste de RSAT**.
2. Selecione **Adicionar existente**.
3. Na página **Adicionar casos de teste ao conjunto**, selecione **Executar consulta**.
4. Selecione o novo caso de teste que foi criado para **Liberar um produto** e selecione **Adicionar casos de teste** no canto inferior direito da página (este botão não é mostrado na ilustração a seguir).

    ![Adicione os casos de teste á página do conjunto.](./media/setup_rsa_tool_100.png)

    O conjunto de testes agora tem dois casos de teste.

    ![Dois casos de teste no conjunto de testes.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Carregar casos de teste no RSAT

1. Abra o RSAT e selecione **Carregar**.
2. Os casos de testes são carregados e você recebe um aviso que informa, "Esta ação substituirá os arquivos de dados de teste do Excel, as alterações locais serão perdidas. Deseja continuar?" Selecione **Sim** para atualizar os arquivos de parâmetros do Excel no sistema local, mas não nos arquivos de parâmetros do Excel que foram carregados para o Azure DevOps.

    ![Esta ação substituirá os arquivos de dados de teste do Excel.](./media/setup_rsa_tool_102.png)

    Os dois casos de teste são carregados, junto com o arquivo de parâmetros do Excel para o primeiro caso de teste. Como você selecionou **Carregar** na última execução, os arquivos de parâmetro são extraídos do Azure DevOps.

    ![Casos de teste carregados.](./media/setup_rsa_tool_103.png)

3. Selecione somente o segundo caso de teste e depois **Novo \> Gerar arquivos de parâmetros e execução de teste**.

#### <a name="edit-the-excel-parameter-file"></a>Edite o arquivo de parâmetros do Excel

1. Selecione somente o segundo caso de teste e depois selecione **Editar** para abrir o arquivo de parâmetros do Excel correspondente.
2. Copie a variável salva **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (consulte a seção [Modificar uma gravação de tarefas existente para criar uma variável salva](#modify-an-existing-task-recording-to-create-a-saved-variable)) do primeiro caso de teste para todos os campos onde o número do produto é usado. Neste caso, você copia a variável para os campos **Número do produto** e **Validar Número do produto** na folha **EcoResProductListPage**.

    ![Campos Número do produto e Validar Número do produto.](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > Variáveis podem ser transmitidos entre testes somente durante a mesma execução de testes. Os nomes de variáveis devem corresponder exatamente.

3. Selecione **Salvar** e feche a pasta de trabalho do Excel.
4. Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel.

#### <a name="run-the-chained-test-cases"></a>Execute os casos de teste encadeados

1. Selecione os dois casos de teste e selecione **Executar**.
2. Verifique se os dois casos de teste foram transmitidos.

    ![Campo de resultado definido como transmitido para os dois casos de teste.](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]