---
title: Configurar a integração direta do FatturaPA com SDI
description: Este artigo fornece informações que ajudarão você a começar a usar o Faturamento eletrônico da Itália e configurar a integração direta do FatturaPA italiano com o sistema do Exchange (SDI).
author: abaryshnikov
ms.date: 07/27/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 363b7b5e3d5abbb990fea8f8ad4d0c1bebf80102
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203159"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Configurar a integração direta do FatturaPA com SDI

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> O Faturamento eletrônico para a Itália talvez não ofereça suporte no momento a todas as funções disponíveis para faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.

Este artigo fornece informações que ajudarão você a começar a usar o Faturamento eletrônico italiano no Finance e no Supply Chain Management. Ele o orienta você pelas etapas de configuração que dependem do país/região para os Regulatory Configuration Services (RCS). Essas etapas complementam as etapas descritas em [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas deste artigo, os pré-requisitos a seguir devem ser atendidos:

- Conclua as etapas em [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).
- Importe o recurso de faturamento eletrônico **FatturaPA italiano (IT)** no RCS do repositório global. Para obter mais informações, consulte a seção [Importar um recurso de faturamento eletrônico do provedor de configuração da Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) do artigo mencionado anteriormente "Introdução ao Faturamento eletrônico".
- Adicione links dos certificados necessários ao ambiente de serviço. Os certificados necessários incluem o certificado de assinatura digital, o certificado de autoridade de certificação (CA) e o certificado de clientes. Para obter mais informações, consulte a seção [Criar segredo de certificado digital](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) do artigo "Introdução à administração do serviço de Faturamento eletrônico".

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Configuração específica de país para o recurso Faturamento eletrônico do FatturaPA italiano (IT)

Conclua os procedimentos a seguir antes de implantar a configuração do aplicativo no aplicativo Finance ou Supply Chain Management conectado.

Esta seção complementa a seção [Configuração específica do país da configuração do aplicativo](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) no artigo "Introdução ao Faturamento eletrônico".

### <a name="create-a-new-feature"></a>Criar um recurso

1. Entre no RCS.
2. No espaço de trabalho do **Relatório eletrônico**, na seção **Provedores de configuração**, marque o provedor de configuração de sua empresa como ativo.
3. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
4. Na página **Recursos de Faturamento eletrônico**, selecione **Adicionar** \> **Com base no recurso existente**.
5. Em **Provedor de configuração da Microsoft**, selecione **FatturaPA italiano (IT)** como um recurso básico, insira um nome e selecione **Criar recurso**.

### <a name="set-up-application-specific-parameters"></a>Configurar parâmetros específicos do aplicativo

1. Na página **Recursos de Faturamento eletrônico**, selecione o recurso a ser editado.
2. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
3. Na guia **Configurações**, selecione uma configuração e, em seguida, selecione **Parâmetros específicos do aplicativo**.
4. Na seção **Pesquisas**, verifique se a pesquisa **Lista de subcategorias de encargos revertidos da Natura** está selecionada.
5. Na seção **Condições**, selecione **Adicionar**.
6. Adicione condições específicas para cada subcategoria definida no sistema e salve suas alterações.

    > [!NOTE]
    > Na coluna **Nome**, você pode selecionar o espaço reservado **\*Vazio\*** ou **\*Não vazio\*** em vez de um valor específico.

### <a name="configure-a-processing-pipeline-for-export"></a>Configurar um pipeline de processamento para exportação

1. Na página **Recursos de Faturamento eletrônico**, selecione o recurso a ser editado.
2. Na guia **Configurações**, selecione **Faturas de venda** e, em seguida, **Editar**.
3. Na seção **Pipeline de processamento**, siga as ações e defina todos os campos obrigatórios:

    - Para a ação **Assinar documento**, no campo **Nome do certificado**, especifique o certificado de assinatura digital.
    - Para a ação **Enviar**, defina os campos **Endereço da URL** e **Certificados**. O valor do campo **Certificados** é uma cadeia de certificados, a primeira que é o certificado da CA raiz (caentrate.cer) e a segunda que é o certificado de clientes.

4. Na seção **Regras de aplicabilidade**, analise as cláusulas e revise ou defina os campos obrigatórios:
    - Revise a cláusula **LegalEntityID** e atualize com o valor correto da sua entidade legal.

5. Selecione **Validar** para garantir que todos os campos obrigatórios sejam definidos.
6. Salve suas alterações e feche a página.
7. Na guia **Configurações**, selecione **Faturas de projeto** e, em seguida, **Editar**.
8. Repita as etapas 3 a 6 para faturas de projeto.

### <a name="configure-the-processing-pipeline-for-import"></a>Configurar o pipeline de processamento para importação

1. Na página **Recursos de Faturamento eletrônico**, selecione o recurso a ser editado.
2. Na guia **Configurações**, selecione **Faturas de importação** e, em seguida, **Editar**.
3. Na seção **Canal de dados**, na guia **Parâmetros**, no campo **Canal de dados**, insira um valor da cadeia de caracteres.
4. Na guia **Regras de aplicabilidade**, defina os campos para a configuração. Você pode usar a cláusula **Canal** padrão passando o valor definido para o campo **Canal de dados** na etapa anterior para o campo **Valor**.

    ![Configurar regras de aplicabilidade.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Selecione **Validar** para garantir que todos os campos obrigatórios sejam definidos.

### <a name="deploy-the-feature"></a>Implantar o recurso

1. Conclua, publique e implante o recurso para o ambiente de serviço. Para obter mais informações, consulte a seção [Implantar o recurso de Faturamento eletrônico no ambiente de serviço](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) do artigo "Introdução ao faturamento eletrônico".
2. Implante o recurso no aplicativo conectado. Para obter mais informações, consulte a seção [Implantar o recurso de Faturamento eletrônico no aplicativo conectado](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) do artigo "Introdução ao faturamento eletrônico".

### <a name="set-up-finance"></a>Configurar o Finance

1. Entre no seu ambiente do Finance.
2. No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o bloco **Microsoft**.
3. Selecione **Repositórios** \> **Global** \> **Abrir**.
4. Selecione e importe o **Modelo de contexto de fatura do cliente** e configurações de **Importação de fatura de fornecedor (IT)**.
5. Acesse **Administração da organização** \> **Configuração** \> **Parâmetros de documentos eletrônicos**.
6. Na guia **Recursos**, localize e selecione o recurso **Fatura eletrônica italiana** e, em seguida, marque a caixa de seleção **Habilitar**.
7. Na guia **Documento eletrônico**, verifique se os campos para **Diário de faturas de clientes** e **Fatura de projeto** são definidos de acordo com as informações em [Configurar a configuração do aplicativo](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Configurar importação de fatura de fornecedor 

1. No Finance, no espaço de trabalho do **Relatório eletrônico**, na seção **Provedores de configuração**, marque o provedor de configuração de sua empresa como ativo.
2. Selecione **Configurações de relatórios**.
3. Selecione **Modelo de contexto de fatura de cliente** e, em seguida, **Criar configuração**.
4. Selecione **Derivar de Nome: Contexto de fatura de cliente, Microsoft** para criar uma configuração derivada.
5. Na versão **Rascunho**, selecione **Designer**.
6. Na árvore **Modelo de dados**, selecione **Mapear modelo para datasource**.
7. Na árvore **Definições**, selecione **DataChannel** e, em seguida, **Designer**.
8. Na árvore **Fontes de dados**, expanda o contêiner **\$Context\_Channel**.
9. No campo **Valor**, selecione **Editar**. 
10. Insira o nome do canal de dados. O nome deve ter no máximo 10 caracteres. Ele deve corresponder ao valor do parâmetro **Canal de dados** do canal de dados do recurso de Faturamento eletrônico no RCS.
11. Salve as alterações e vá para **Configurações de relatórios** \> **Concluir versão de configuração**.
12. Na guia **Canais externos**, na seção **Canais**, selecione **Adicionar**.
13. No campo **Canal**, insira o valor **\$Context Channel**.
14. Insira os valores nos campos **Descrição** e **Empresa**.
15. No campo **Contexto do documento**, selecione a nova configuração derivada do **Modelo de contexto da fatura do cliente**. A descrição do mapeamento deve ser **Contexto de canal de dados**.
16. Na guia **Importar fontes**, selecione **Adicionar** e, em seguida, defina os seguintes valores:

    - **Nome:** OutputFile
    - **Nome da entidade de dados:** Cabeçalho da fatura de fornecedor (**Entidade de dados:** VendorInvoiceHeaderEntity)
    - **Mapeamento de modelos:** Importação da fatura de fornecedor (TI)

> [!NOTE]
> Se você tiver faturas de fornecedor de importação de diferentes fontes, poderá criar vários canais externos e várias configurações derivadas que têm diferentes valores **\$Context Channel**. Por exemplo, você pode desejar importar faturas de fornecedor para diferentes entidades legais.

## <a name="proxy-server-setup"></a>Configuração do servidor proxy

Esta seção fornece informações que ajudarão você a definir e configurar o serviço de proxy para comunicação entre o sistema do Exchange (SDI) e o serviço de Faturamento eletrônico.

### <a name="create-an-app-registration"></a>Criar um registro de aplicativo

1. Use o seguinte script do Windows PowerShell para criar um certificado autoassinado para autenticação de serviço a serviço (S2S).

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Salve o arquivo de certificado .pfx no cofre de chaves e exclua a cópia local.
3. Entre no [portal do Azure](https://portal.azure.com) como administrador.
4. Crie um registro de aplicativo para o serviço de proxy SDI.

    1. Vá para **Registros de aplicativo**, crie um registro e defina os seguintes valores para ele:

        - **Nome:** Cliente proxy SDI
        - **Tipos de conta com suporte:** Contas somente neste diretório organizacional (único locatário)

    2. Selecione **Registrar** e, em seguida, selecione o registro de aplicativo que você acabou de criar.
    3. Vá para **Permissões de API** e selecione **Conceder consentimento do administrador**.
    4. Vá para **Certificados e segredos**, selecione **Carregar certificado** e carregue o arquivo de certificado .cer para autenticação S2S.
    5. Vá para **Aplicativos empresariais** e selecione o aplicativo criado.
    6. Salve os valores **ID do aplicativo** (ID do cliente) e **ID do objeto** para o aplicativo.
    7. A equipe de serviço de faturamento deve conceder o acesso do aplicativo ao serviço. Envie os valores dos seguintes parâmetros para <D365EInvoiceSupport@microsoft.com>:

        - ID do Locatário do AAD
        - ID do ambiente do LCS
        - ID do Aplicativo
        - ID do Objeto

5. No RCS, adicione o aplicativo à lista de aplicativos para o ambiente de serviço.

    1. Vá para **Recursos de globalização** \> **Ambientes** \> **Faturamento eletrônico** \> **Ambientes de serviço** e selecione seu ambiente.
    2. Na seção **Aplicativos**, adicione uma linha à grade e insira o nome e a ID do objeto do aplicativo.

        ![Adicionar o aplicativo ao ambiente de serviço.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Selecione **Salvar** e **Publicar**.

### <a name="create-an-azure-virtual-machine"></a>Criar uma máquina virtual do Azure

1. No [portal do Azure](https://portal.azure.com), vá para **Máquinas virtuais** e selecione **Criar novo**.
2. Na guia **Básico**, selecione a assinatura e o grupo de recursos. Os valores devem ser a assinatura e o grupo de recursos em que o seu cofre de chaves e o armazenamento de Blobs estão localizados.
3. Selecione a região. Esse valor deve ser a região em que seu ambiente do Finance é implantado.
4. Adicione o nome de usuário e senha do administrador e salve-os no cofre de chaves.
5. No campo **Selecionar portas de entrada**, selecione **HTTPS (443)** e **RPD (3389)**.

    > [!NOTE]
    > É recomendável desabilitar a porta **RDP (3389)** quando o sistema for para produção. É possível habilitá-la novamente se você precisar se conectar à máquina virtual (VM) para fins de solução de problemas.

    ![Configurar os campos na guia Básico para criar uma VM do Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. Na guia **Discos**, na guia rápida **Avançado**, marque a caixa de seleção **Usar discos gerenciados**. Deixe a caixa de seleção **Disco de SO efêmero** desmarcada.

    ![Configurar os campos na guia Discos para criar uma VM do Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. Na guia **Rede**, no campo **IP público**, selecione **Criar novo**.

    ![Configurar os campos na guia Rede para criar uma VM do Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. Na caixa de diálogo **Criar endereço IP público**, no grupo do campo **SKU**, selecione a opção **Padrão**. No grupo de campos **Atribuição**, selecione a opção **Estático**.

    ![Criar um endereço IP público.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. Na guia **Gerenciamento**, desmarque a caixa de seleção **Desligamento automático** para desabilitar o desligamento automático.
10. Defina o campo **Atualizações de SO convidado** como **Manual** e, em seguida, defina outras políticas.
11. Revise e cria a VM.
12. Na nova VM, vá para **Identidade** \> **Sistema atribuído** e defina a opção **Status** como **Ativado**.
13. Conceda acesso à VM ao cofre de chaves.

    1. No cofre de chaves, vá para **Controle de acesso (IAM)** \> **Atribuições de função**.
    2. Selecione **Adicionar atribuição de função** e, em seguida, defina os campos a seguir:

        1. No campo **Função**, especifique o **Usuário de segredos do cofre de chaves**.
        2. No campo **Atribuir acesso a**, especifique **Máquina virtual**.
        3. No campo **Assinatura**, especifique sua assinatura.
        4. No campo **Selecionar**, especifique sua VM.

    3. Vá para **Políticas de acesso**.
    4. Selecione **Adicionar política de acesso** e, em seguida, defina os campos a seguir:

        1. No campo **Entidade de segurança selecionada**, selecione sua VM.
        2. Na seção **Certificado**, selecione as permissões **Listar** e **Obter**.

14. No [portal do Azure](https://portal.azure.com), vá para **Endereços IP públicos** e selecione o endereço IP que foi criado na VM.
15. Vá para **Configuração** e defina o nome do Sistema de Nome de Domínio (DNS).

### <a name="prepare-the-proxy-service-environment"></a>Preparar o ambiente do serviço de proxy

Siga estas etapas na máquina em que o serviço de proxy está hospedado.

1. Conecte-se à VM usando a conexão de área de trabalho remota.
2. Abra o snap-in de certificados do computador local. Para obter mais informações, consulte [Tutorial: Exibir certificados com o snap-in do MMC](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Importe o certificado **caentrate.cer** para produção e o **CAEntratetest.cer** para teste no [Armazenamento de autoridades de certificação raiz confiáveis](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**CAEntratetest.cer** é o certificado de CA raiz fornecido pela autoridade.)
4. No Painel de controle, abra **Ativar ou desativar recursos do Windows** ou vá para **Gerenciador de servidores** \> **Adicionar funções e recursos** para o sistema operacional (SO) do servidor e ative os recursos de Serviços de Informações da Internet (IIS):

    - Ferramentas de gerenciamento da Web
        - Console de gerenciamento de IIS
    - Serviços da World Wide Web
        - Recursos de desenvolvimento de aplicativos
            - Extensibilidade .NET 4.7 (ou 4.8)
            - ASP
            - ASP.NET 4.7 (ou 4.8)
            - CGI
            - Extensões de ISAPI
            - Filtros de ISAPI
        - Recursos de HTTP comuns
            - Documento padrão
            - Navegação em diretórios
            - Erros HTTP
            - Conteúdo estático
        - Integridade e diagnóstico
            - Registro em log HTTP
            - Rastreando
        - Recursos de desempenho
            - Compactação de conteúdo estático
        - Segurança
            - Filtragem de solicitações

    ![Ativar recursos de IIS.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Configurar o serviço de proxy SDI no IIS

1. No Microsoft Dynamics Lifecycle Services (LCS), acesse a Biblioteca de ativos compartilhados e selecione **Pacote de dados** como tipo de dados.
2. Encontre o **Proxy de SDI de serviço de Faturamento eletrônico** e baixe-o para a VM.
3. Configure o servidor.

    1. Descompacte a pasta de arquivos **Proxy de SDI do serviço de Faturamento eletrônico** baixada.
    2. Na pasta **src\\FattureService**, abra o arquivo **appsettings.json** e defina os seguintes parâmetros:

        - **KeyVaultUri** – Especifique o endereço do cofre de chaves que armazena o certificado de cliente para o serviço de faturamento.
        - **TenantId** – Especifique o identificador global exclusivo (GUID) do locatário do cliente.
        - **EnvironmentId** – Especifique a ID do ambiente do LCS.
        - **ClientId** – Especifique a ID do aplicativo do registro do aplicativo de serviços intermediários no locatário do cliente.
        - **ClientCertificateName** – Especifique o nome do certificado S2S no cofre de chaves.
        - **SecurityServiceClientOptions.Endpoint** – Especifique a URL do serviço de segurança.
        - **SecurityServiceClientOptions.Resource** – Especifique o escopo para o qual obter o token.
        - **InvoicingServiceClientOptions.Endpoint** – Especifique o ponto de extremidade do serviço de faturamento. Esse valor deve ser o mesmo ponto de extremidade usado para o RCS e o Finance.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** – Especifique o nome do ambiente de serviço. Esse valor deve ser o nome do seu ambiente do Finance.
        - **NotificationsFolder** – Especifique a pasta na qual salvar os arquivos de notificação de entrada.

    3. No arquivo **web. config**, encontre a linha a seguir e adicione a impressão digital do certificado do servidor proxy.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Quando o sistema vai para a produção, você pode alterar alguns valores no arquivo web.config para ajudar a reduzir o volume de informações de log coletadas e ajudar a economizar espaço em disco. No nó **\<system.diagnostics\>\<source\>**, altere o valor do **switchValue** para **Critical,Error**. Para obter mais informações, consulte [Visualizador de rastreamento do serviço do MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Abra o Gerenciador do IIS. Na árvore à esquerda, permaneça no nó raiz. À direita, selecione **Certificados de servidor**.

    ![Selecionar certificados de serviço no Gerenciador do IIS.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Abra o menu e selecione **Importar**.
6. Na caixa de diálogo **Importar certificado**, no campo **Arquivo do certificado (.pfx)**, especifique o caminho do arquivo .pfx do certificado do servidor proxy.

    ![Especificar o arquivo do certificado do serviço de proxy.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Selecione e segure (ou clique com o botão direito do mouse) em **Sites** e selecione **Adicionar site**.
8. Na caixa de diálogo **Adicionar site**, no campo **Nome do site**, insira um nome para o site.
9. No campo **Caminho físico**, aponte para a pasta **src\\FattureService**.
10. No campo **Tipo de associação**, selecione **https**.
11. No campo **Nome do host**, especifique o nome do host.
12. Deixe os campos **Endereço IP** e **Porta** definidos com os valores padrão.
13. Verifique se a caixa de seleção **Exigir Indicação de Nome de Servidor** está desmarcada, porque SDI não oferece suporte a essa tecnologia.
14. No campo **Certificado SSL**, selecione o certificado do servidor proxy importado.
15. No campo **Pool de aplicativos**, especifique um grupo para o site e anote seu nome (por exemplo, **SdiAppPool**).

    ![Adicionar um site.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Depois de concluir a criação do site, abra o menu para **Configurações de SSL**.

    ![Abrir o menu para configurações de SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Marque a caixa de seleção **Exigir SSL** e, no grupo de campos **Certificados do cliente**, selecione a opção **Exigir**.

    ![Definir configurações de SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Abra **Navegação em diretórios** e selecione **Habilitar**.
19. Em qualquer navegador da Web, vá para **serverDNS/TrasmissioneFatture.svc**. Uma página padrão sobre o serviço deve ser exibida.

    ![Verificar o serviço em um navegador.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Crie as seguintes pastas para armazenar logs e arquivos:

    - **C:\\Logs\\** – Armazene arquivos de log aqui. Esses arquivos podem ser exibidos pelo [Visualizador de rastreamento de serviço do MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C:\\Files\\** – Armazene todos os arquivos de resposta aqui.

21. No Explorador de Arquivos, conceda acesso de **NETWORK SERVICE** e **IIS AppPool\\SdiAppPool** (ou **IIS AppPool\\DefaultAppPool** se estiver usando o pool padrão) às pastas **Logs** e **Arquivos**.

    1. Selecione e segure (ou clique com o botão direito do mouse) em uma das pastas e selecione **Propriedades**.
    2. Na caixa de diálogo **Propriedades**, na guia **Segurança**, selecione **Editar**.
    3. Adicione os usuários se não estiverem listados.
    4. Repita as etapas 1 a 3 para a outra pasta.

    ![Adicionar permissões ao usuário de serviço.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Aviso de privacidade 

Habilitar o recurso **Fatura eletrônica italiana** pode exigir o envio de dados limitados. Esses dados incluem a ID de registro de imposto da organização. Um administrador pode habilitar e desabilitar o recurso de fatura eletrônica italiana. Para desabilitar o recuso, siga estas etapas.

1. Acesse **Administração da organização** \> **Configuração** \> **Parâmetros de documentos eletrônicos**.
2. Na guia **Recursos**, selecione as linhas que contêm o recurso **Fatura eletrônica italiana** e, em seguida, selecione **Desabilitar agora**.

Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Para obter mais informações, consulte a seção "Aviso de privacidade" da documentação de recursos específicos do país/região.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
