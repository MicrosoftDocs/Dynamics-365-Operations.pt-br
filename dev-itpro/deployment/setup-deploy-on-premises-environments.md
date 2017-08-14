---
title: Configurar e implantar ambientes locais
description: "Este tópico fornece informações sobre como planejar, configurar e implantar um ambiente local."
author: sarvanisathish
manager: AnnBe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations, Unified Operations
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: d100f6dbcbdf8f4c12ab04670fb598a88d48d84b
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: pt-br
ms.lasthandoff: 08/10/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>Configurar e implantar ambientes locais

Este documento descreve como planejar sua implantação, configurar a infraestrutura e implantar o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (local).

## <a name="finance-and-operations-components"></a>Componentes do Finance and Operations

O aplicativo Finance and Operations consiste nos três principais componentes:

- AOS (Servidor de Objetos de Aplicativo)
- Business Intelligence (BI)
- Financial Reporting/Management Reporter

Esses componentes dependem do seguinte software do sistema:

- Microsoft Windows Server 2016
- Microsoft SQL Server 2016 SP1, que possui os seguintes recursos:

    - A pesquisa de índice de texto completo está habilitada.
    - SQL Server Reporting Services (SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > O aplicativo não será executado, se a Pesquisa de texto completo não estiver habilitada.

- SQL Server Management Studio
- Service Fabric Autônomo do Microsoft Azure
- Windows PowerShell 5.0 ou posterior
- Active Directory Federation Services (AD FS) no Windows Server 2016

  O controlador de domínio deve ser Windows Server 2012 R2 ou posterior com um nível de domínio funcional de 2012 R2 ou superior

  Para obter mais informações sobre níveis funcionais de domínio, consulte: 
  - [O que são níveis funcionais do Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Noções básicas dos níveis funcionais dos Serviços de domínio Active Directory](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Lifecycle Services

Os bits do Finance and Operations são distribuídos através do Microsoft Dynamics Lifecycle Services (LCS). Antes de implantar, você deve comprar as chaves de licença através do canal [Contratos empresarial](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) e configurar um projeto local no LCS. As implantações podem ser iniciadas somente através de LCS. Para obter mais informações sobre como configurar projetos locais no LCS, consulte [Criar um projeto local no Lifecycle Services](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Autenticação

O aplicativo local trabalha com AD FS. Para interagir com o LCS, você também deve configurar o Azure Active Directory (Azure AD).

## <a name="standalone-service-fabric"></a>Service Fabric autônomo

O Finance and Operations usa Service Fabric autônomo. Para obter mais informações, consulte a [documentação do Service Fabric](/azure/service-fabric/).

## <a name="infrastructure"></a>Infraestrutura

O Finance and Operations é projetado para trabalhar em uma arquitetura hiperconvergente. A configuração de hardware inclui os seguintes componentes:

- O cluster do Service Fabric autônomo que é baseado nas máquinas virtuais (VMs) do Windows Server 2016
- SQL Server (SQL Clusterizado e Always-On são suportados)
- AD FS para autenticação
- Compartilhamento de arquivo da versão 3 do Server Message Block (SMB) para armazenamento
- Opcional: Microsoft Office Server 2017

Para obter mais informações, consulte [Requisitos do sistema](../get-started/system-requirements.md) e diretrizes de dimensionamento.

### <a name="hardware-layout"></a>Layout de hardware

Planejar sua infraestrutura e cluster do Service Fabric, com base no dimensionamento recomendado em [Dimensionamento de hardware para ambientes locais](../get-started/hardware-sizing-on-premises-environments.md). Para obter mais informações sobre como planejar o cluster do Service Fabric, consulte [Planejar e preparar sua implementação autônoma do cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

A tabela a seguir mostra um exemplo do layout de hardware. Esse exemplo é usado em todo este tópico para ilustrar a instalação.

> [!NOTE]
> O nó principal do cluster do Service Fabric deve ter pelo menos três nós. Neste exemplo, o **OrchestratorType** será designado como o tipo de nó principal.

| Finalidade da máquina                                 | Nome da máquina    | Endereço IP    |
|-------------------------------------------------|-----------------|---------------|
| Controlador de domínio                               | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| Servidor de arquivos                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| SQL Always-On cluster                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Cliente                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Cluster do Service Fabric/AOS 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Cluster do Service Fabric/AOS 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Cluster do Service Fabric/AOS 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Cluster do Service Fabric/Orchestrator 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Cluster do Service Fabric/Orchestrator 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Cluster do Service Fabric/Orchestrator 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Cluster do Service Fabric/Nó do Management Reporter | SQLAOSMR1       | 10.179.108.18 |
| Cluster do Service Fabric/nó de SSRS 3                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Configurar

### <a name="prerequisites"></a>Pré-requisitos

Antes de começar a instalação, os seguintes pré-requisitos devem ser atendidos. A instalação destes pré-requisitos está fora do escopo deste documento.

- O Active Directory Domain Services (AD DS) está instalado e configurado em sua rede.
- O AD FS está implantado.
- SQL Server, SSRS e Management Studio estão instalados.

### <a name="overview"></a>Visão Geral

As etapas a seguir devem ser concluídas para configurar a infraestrutura para Finance and Operations.

1. Planejar o nome de domínio e as zonas de DNS
2. Planejar e adquirir os certificados
3. Planejar os usuários e contas de serviço
4. Criar zonas DNS e adicionar registros A
5. Adicionar VMs ao domínio
6. Adicionar o software de pré-requisito às VMs
7. Baixar scripts de configuração do LCS
8. Descrever a configuração
9. Instalar certificados
10. Configurar um cluster do Service Fabric autônomo
11. Configurar a conectividade de LCS do locatário
12. Configurar o armazenamento do arquivo
13. Configurar o SQL Server
14. Configurar os bancos de dados
15. Criptografar credenciais
16. Configurar SSRS
17. Configurar AD FS

### <a name="plan-your-domain-name-and-dns-zones"></a>Planejar o nome de domínio e as zonas de DNS

Recomenda-se usar um nome de domínio publicamente registrado para a instalação de produção de AOS. Dessa forma, ele pode ser acessado fora da rede, caso o acesso externo seja necessário.

Por exemplo, se o domínio da empresa é contoso.com, sua zona do Finance and Operations (local) pode ser d365ffo.onprem.contoso.com e os nomes do host podem ser os seguintes:

- ax.d365ffo.onprem.contoso.com para máquinas AOS
- sf.d365ffo.onprem.contoso.com para o cluster do Service Fabric

### <a name="plan-and-acquire-your-certificates"></a>Planejar e adquirir os certificados

Certificados SSL necessários para proteger um cluster do Service Fabric e todos os aplicativos que são implantados. Para cargas de trabalho de produção e área restrita, recomendamos que você adquira certificados de uma autoridade de certificação (CA), como [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/), [Symantec](https://www.websecurity.symantec.com/ssl-certificate), [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate) ou [GlobalSign](https://www.globalsign.com/en/ssl/). Se seu domínio estiver configurado com [Serviços de Certificados do Active Directory](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx) (AD CS), você pode criar certificados através de AD CS. Cada certificado deve conter uma chave privada criada para trocas de chaves, e devem ser exportável para um arquivo de Troca de Informações Pessoais (.pfx).

Os certificados autoassinados podem ser usados apenas para fins de teste. Para a conveniência, os scripts de instalação incluem os scripts que geram e exportam certificados autoassinados. Como mencionamos, esses certificados devem ser usados somente para fins de teste.

| Finalidade                                      | Explicação | Requisitos adicionais |
|----------------------------------------------|-------------|-------------------------|
| Certificado SSL do SQL Server                   | Este certificado é usado para criptografar os dados que são transmitidos pela rede entre uma instância do SQL Server e um aplicativo cliente. | <p>O nome de domínio do certificado deve corresponder ao nome de domínio totalmente qualificado de (FQDN) da instância ou listener do SQL Server.</p><p>Por exemplo, se o listener de SQL for hospedado na máquina DAX7SQLAOSQLA, o nome de DNS do certificado será DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Certificado do servidor Service Fabric            | Este certificado é usado para ajudar a proteger a comunicação nó a nó entre os nós do Service Fabric. Este certificado também é usado como o certificado do servidor que é apresentado ao cliente que conecta-se ao cluster. | <p>O nome de domínio do certificado deve corresponder à zona de DNS na qual o AOS e o Service Fabric estão hospedados.</p><p>Por exemplo, nome de domínio de certificado pode ser \*.onprem.contoso.com ou \*.contoso.com.</p><p>Se você usar um certificado curinga, o caractere curinga será aplicado somente a um nível. Um subdomínio, nome alternativo para o requerente (SAN), deve ser aplicado ao certificado, se ele tiver mais de um nível, como \*.contoso.com no exemplo anterior.</p> |
| Certificado do cliente do Service Fabric            | Este certificado é usado pelos clientes para exibir e gerenciar o cluster do Service Fabric. | |
| Certificado de codificação                     | Este certificado é usado para criptografar dados sigilosos, como as senhas do SQL Server e senhas da conta do usuário. | <p>O uso da chave do certificado deve incluir a codificação de dados (10) e não devem inclui Autenticação do servidor ou Autenticação do cliente.</p><p>Para obter mais informações, consulte [Gerenciando segredos nos aplicativos do Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| Certificado SSL do AOS                          | <p>Este certificado também é usado como o certificado do servidor que é apresentado ao cliente do site do AOS. Também é usado para habilitar certificados do WCF (Windows Communication Foundation)/SOAP (Simple Object Access Protocol).</p><p>O certificado do servidor Service Fabric pode ser usado aqui se for um certificado curinga.</p> | <p>O nome de domínio do certificado deve corresponder à zona de DNS na qual o AOS e o Service Fabric estão hospedados.</p><p>Por exemplo, nome de domínio de certificado pode ser \*.d365ffo.onprem.contoso.com, \*.onprem.contoso.com ou \*.contoso.com.</p><p>Se você usar um certificado curinga, o caractere curinga será aplicado somente a um nível. Um subdomínio, SAN, deve ser aplicado ao certificado, se ele tiver mais de um nível, como \*.contoso.com no exemplo anterior.</p> |
| Certificado de autenticação da sessão           | Este certificado é usado pelo AOS para ajudar a proteger informações de sessão de um usuário. | Esse também é o certificado de **Compartilhamento de arquivos** que será usado no momento de implementação de LCS. |
| Certificado de criptografia de dados e de assinatura de dados | Esses certificados são usados pelo AOS para criptografar dados sigilosos. | |
| Certificado de cliente do Financial Reporting       | Este certificado é usado para ajudar a proteger a comunicação nó a nó entre os nós dos serviços do Financial Reporting e do AOS. | |
| Certificado de relatório                        | Este certificado é usado para ajudar a proteger a comunicação entre SSRS e AOS. | |
| Certificado de agente do local (local)           | <p>Este certificado é usado para ajudar a proteger a comunicação entre um agente local que é hospedado no local e LCS.</p><p>O certificado habilita o agente local para agir em nome do locatário do Azure AD e para comunicar-se com o LCS para orquestrar e monitorar implantações.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>Planejar os usuários e contas de serviço

É necessário criar várias contas de usuário ou serviço para que o Finance and Operations (local) trabalhe. É necessário criar uma combinação de contas de serviço gerenciadas por grupos (gMSAs), contas de domínio e contas de SQL. A tabela a seguir mostra as contas de usuário, suas finalidades e nomes de exemplo que serão usados neste tópico.

| Conta de usuário                                            | Tipo           | Finalidade | Nome de usuário |
|---------------------------------------------------------|----------------|---------|-----------|
| Conta de serviço do aplicativo Financial Reporting         | gMSA           |         | Contoso\\svc-FRAS$ |
| Conta de serviço do processo do Financial Reporting             | gMSA           |         | Contoso\\svc-FRPS$ |
| Conta de serviço do designer de um clique do Financial Reporting | gMSA           |         | Contoso\\svc-FRCO$ |
| Conta de serviço do AOS                                     | gMSA           | Esse usuário deve ser criado para revisão futura. Pretendemos habilitar o AOS para trabalhar com o gMSA em versões futuras. Criando este usuário no momento da instalação, você ajudará a garantir uma transição completa para o gMSA. | Contoso\\svc-AXSF$ |
| Conta de serviço do AOS                                     | Conta de domínio | O AOS usa esse usuário na versão de GA. | Contoso\\AXServiceUser |
| O usuário admin do BD SQL de AOS                                   | Usuário SQL       | O Finance and Operations usa este usuário para se autenticar ao SQL\*. Esse usuário também será substituído pelo usuário de gMSA em versões futuras. | AXDBAdmin |
| Conta de serviço do agente de implantação local                  | gMSA           | Esta conta será usada pelo agente local para orquestrar a implantação em vários nós. | Contoso\\Svc-LocalAgent$ |

\* O nome do usuário e a senha de SQL para autenticação de SQL são protegidos porque eles são criptografados e armazenados no compartilhamento de arquivo.

### <a name="create-dns-zones-and-add-a-records"></a>Criar zonas DNS e adicionar registros A

O DNS é integrado a AD DS e permite organizar, gerenciar e localizar recursos em uma rede. Crie uma zona de pesquisa direta de DNS e registros A para o nome de host de AOS e o cluster do Service Fabric. Nesta configuração de exemplo, o nome da zona DNS é d365ffo.onprem.contoso.com, e os registros A/nomes do host são os seguintes:

- **ax**.d365ffo.onprem.contoso.com para máquinas AOS
- **sf**.d365ffo.onprem.contoso.com para o cluster do Service Fabric

#### <a name="add-a-dns-zone"></a>Adicionar uma zona DNS

Use o procedimento a seguir para adicionar uma zona DNS.

1. Entre na máquina do controlador de domínio, clique em **Iniciar** e inicie o Gerenciador de DNS, digitando **dnsmgmt.msc**.
2. Clique com o botão direito do mouse no nome do controlador de domínio, em seguida, clique em **Nova Zona** \> **Próximo**.
3. Selecione **Zona principal**.
4. Deixe a caixa de seleção **Armazenar a zona no Active Directory (disponível somente se o Servidor DNS for um controlador de domínio gravável)** marcada e clique em **Próximo**.
5. Selecione **Para todos os servidores DNS que são executados nos controladores de domínio neste domínio: Contoso.com**, e depois clique em **Próximo**.
6. Selecione **Zona de Pesquisa Direta**, e depois clique em **Próximo**.
7. Insira o nome da zona de sua instalação e clique em **Próximo**. Por exemplo, insira **d365ffo.onprem.contoso.com**.
8. Selecione **Não permitir atualizações dinâmicas**, e clique em **Próximo**.

#### <a name="set-up-an-a-record-for-aos"></a>Configurar um registro A para AOS

Na nova zona de DNS, crie um registro A que seja nomeado **ax.d365ffo.onprem.contoso.com** para **cada** Nó de cluster do Service Fabric do tipo **AOSNodeType**. Não crie registros A para os outros tipos de nós.

1. Clique com o botão direito na nova zona e depois clique em **Novo Host**.
2. Insira o nome e o endereço IP de nó do Service Fabric (por exemplo, 10.179.108.12) e clique em **Adicionar Host**.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Configurar um registro A para AOS

Na nova zona de DNS, crie um registro A que seja nomeado **sf.d365ffo.onprem.contoso.com** para **cada** Nó de cluster do Service Fabric do tipo **OrchestratorType**. Não crie registros A para os outros tipos de nós.

1. Clique com o botão direito na nova zona e depois clique em **Novo Host**.
2. Insira o nome e o endereço IP de nó do Service Fabric (por exemplo, 10.179.108.15) e clique em **Adicionar Host**.

#### <a name="join-vms-to-the-domain"></a>Adicionar VMs ao domínio

Adicione cada um dos VMs ao domínio, concluindo as etapas de [Como adicionar o Windows Server 2015 a um domínio do Active Directory](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). Como alternativa, use o script do Windows PowerShell.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
Depois que as VMs forem adicionadas ao domínio, adicione as Contas de serviço do AOS (Contoso\svc-AXSF$, Contoso\svc-AXSF$ ) ao grupo de administradores locais. Você pode verificar o artigo [Adicionar um membro ao grupo local](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx) para saber como fazer isso.

#### <a name="disable-user-access-control"></a>Desativar Controle de Acesso do Usuário 

Execute o script a seguir para desabilitar o Controle de Acesso do Usuário em **cada** nó do Service Fabric.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> Você deve reinicializar o nó depois que o script for concluído com êxito.

#### <a name="add-prerequisite-software-to-vms"></a>Adicionar o software de pré-requisito às VMs

A tabela a seguir lista o software de pré-requisito que deve ser aplicado às máquinas de cada tipo de nó.

> [!NOTE]
> Você terá que reiniciar o computador depois de instalar os componentes.

| Tipo de nó | Componente | Comando |
|-----------|-----------|---------|
| AOS       | SNAC – driver de ODBC | Consulte [Microsoft ODBC Driver 13.1 para SQL Server - Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| AOS       | A versão 2.0–3.5 (CLR 2.0) do Microsoft .NET Framework | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AOS       | A versão 4.0–4.6 (CLR 4.0) do Microsoft .NET Framework | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AOS       | Serviços de Informações da Internet (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| AOS       | Microsoft SQL Server Management Studio 2016 | |
| AOS       | Pacotes redistribuíveis do Microsoft Visual C++ para Microsoft Visual Studio 2013 | Consulte [Pacotes redistribuíveis do Microsoft Visual C++ para Microsoft Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |
| AOS       | Mecanismo de Banco de Dados do Microsoft Access 2010 Redistribuível | Consulte [Mecanismo de Banco de Dados do Microsoft Access 2010 Redistribuível](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| BI        | A versão 2.0–3.5 (CLR 2.0) do .NET Framework | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| BI        | A versão 4.0–4.6 (CLR 4.0) do .NET Framework | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| BI        | Microsoft SQL Server 2016 SP1 | |
| BI        | Management Studio 2016 | |
| BI        | SQL Server Reporting Services 2016 no modo **Nativo** | |
| MR        | A versão 2.0–3.5 (CLR 2.0) do .NET Framework | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | A versão 4.0–4.6 (CLR 4.0) do .NET Framework | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Pacotes redistribuíveis do Microsoft Visual C++ para Visual Studio 2013 | Consulte [Pacotes redistribuíveis do Microsoft Visual C++ para Microsoft Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |

#### <a name="download-setup-scripts-from-lcs"></a>Baixar scripts de configuração do LCS

Fornecemos vários scripts para ajudar a melhorar a experiência de instalação. Siga estas etapas para baixar os scripts de instalação de LCS.

1. Entre no LCS (<https://lcs.dynamics.com/v2>).
2. No painel, clique no bloco **Biblioteca de ativos compartilhados**.
3. Clique na guia **Modelo**.
4. Na grade, selecione a linha **Dynamics 365 for Operations - Scripts de implantação locais**.
5. Clique em **Versões** e baixe a versão mais recente dos scripts.

### <a name="describe-your-configuration"></a>Descrever a configuração

Esta seção fornece informações sobre os scripts que você deve executar. Os scripts são discutidos na ordem em que você deve executá-los. Para executar os scripts, preencha o modelo do arquivo em $(downloadPath)\\ConfigTemplate.xml. O arquivo ConfigTemplate.xml descreve os clusters do Service Fabric, os certificados que são usados para configurá-los e as contas que devem
ter acesso aos certificados relevantes. No exemplo que é fornecido, os valores são preenchidos da infraestrutura do exemplo que é descrita neste tópico. O arquivo de modelo será usado na próxima seção.

#### <a name="create-the-domain-account-for-a-service-user"></a>Crie a conta de domínio para um usuário de serviços

Execute o seguinte comando criar a conta de usuário do domínio, contoso\\AXServiceUser.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>Criar gMSAs

1. Altere o diretório para **$ (DownloadPath)**, e execute o seguinte comando do Windows PowerShell.

    > [!NOTE]
    > Este script não cria os usuários. Em vez disso, ele imprime os comandos que devem ser executados na máquina do controlador de domínio.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Copiar a saída do comando para uma janela do Windows PowerShell. Certifique-se de que as divisões de linha foram removidas e execute as linhas na máquina do controlador de domínio do Active Directory usando os privilégios elevados (clique com o botão direito e clique em **Executar como administrador**).
3. Execute o seguinte script na máquina do controlador de domínio do Active Directory para validar se as contas foram criadas com êxito. Verifique se o script é executado após você substituir o padrão que corresponde à convenção de nomeação de contas de serviço.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Execute o script Export-AddGMSAsONVMScript.ps1 na máquina cliente. Este script gera os scripts que são executados em cada VM do Service Fabric e os adiciona a uma pasta que corresponde a cada nome da VM.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>Parar IIS

Use o protocolo RDP para conectar-se cada tela VM do Service Fabric e para concluir as etapas manuais em [Iniciar ou parar o Servidor Web (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). Como alternativa, use o seguinte script de Windows PowerShell usando RDP para conectar-se cada VM do Service Fabric.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
_O recurso de IIS deve ser instalado, mas desativado, pois há algumas dependências para o dlls de IIS no produto._

### <a name="install-certificates"></a>Instalar certificados

1. Se você adquiriu certificados que foram anteriormente listado neste tópico CA válido, preencha o nome de arquivo .pfx e a impressão digital dos certificados no arquivo ConfigTemplate.xml. Defina o atributo **generateSelfSignedCert** como **False** e o atributo **exportable** como **False**. Copie os arquivos .pfx para a pasta $(DownloadPath)\\InfrastructureScripts\\Certs.
2. Se estiver usando certificados autoassinados (somente para fins de teste), execute o seguinte script. Para criar certificados auto-assinados, no arquivo ConfigTemplate.xml, certifique-se de que **generateSelfSignedCert** foi definido como **True** e **exportable** foi definido como **True**. O script atualizará o XML com a impressão digital dos certificados.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Exporte os novos certificados a chave privada (arquivo .pfx). Use o script a seguir para gerar e executar os comandos de exportação no Windows PowerShell. Os arquivos .pfx serão inseridos na pasta Certificados.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Os certificados devem ter sido instalados e estar presentes em cert:\\CurrentUser\\My. Os certificados também devem ser exportáveis.

    Se estiver usando certificados autoassinados, ignore a próxima seção. Você não deve concluir este procedimento.

4. Depois de exportar ou copiar os arquivos .pfx para a pasta $(DownloadPath)\\InfrastructureScripts\\Certs, execute os seguintes comandos para gerar scripts que serão colocados nas pastas que corresponde às VMs.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. Copie os scripts em cada pasta para as VMs que correspondem ao nome da pasta.
6. Em cada VM, execute os seguintes scripts na ordem em que eles aparecem.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Configurar um cluster do Service Fabric autônomo

1. Execute o seguinte comando para gerar o arquivo ClusterConfig.json.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    Para obter mais informações, consulte, [Etapa 1B: Criar um cluster em várias máquinas](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster), [Proteger um cluster autônomo no Windows usando certificados X.509](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security) e [Criar um cluster autônomo em execução no Windows Server](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Baixe o [Pacote de instalação autônoma do Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) para um dos nós do Service Fabric. Depois que o arquivo zip for baixado, desbloqueie-o, clicando com o botão direito no arquivo zip e clicando em **Propriedades**. Na caixa de diálogo, marque a caixa de seleção **Desbloquear** no canto inferior direito.
3. Copie o arquivo zip para um dos nós no cluster do Service Fabric e descompacte-o.
4. Execute os seguintes comandos para criar uma regra de firewall de entrada nas portas 443 e 445 em todos os nós.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Execute os seguintes comandos para criar uma regra de firewall de entrada na porta 80 para o nó de SSRS apenas.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Copie o arquivo ClusterConfig.json para sua localização de instalação descompactada do Service Fabric autônomo.
7. Navegue até o local de instalação descompactado no Windows PowerShell usando os privilégios elevados e execute o seguinte comando para testar o ClusterConfig.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Se o teste for bem-sucedido, execute o seguinte comando para implantar o cluster.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. Depois que o cluster for criado, abra o Service Fabric Explorer em qualquer máquina cliente para validar a instalação:

    1. Instale o certificado do cliente do Service Fabric em CurrentUser\\My, se ele ainda não estiver instalado.
    2. Vá para **Configurações do IE** \> **Modo de Compatibilidade** e desmarque a caixa de seleção **Exibir sites da Intranet no modo de compatibilidade**.
    3. Vá para `https://sf.d365ffo.onprem.contoso.com:19080`, onde sf.d365ffo.onprem.contoso.com é o nome do host do cluster do Service Fabric que é especificado na zona. Se a resolução de nome de DNS não for configurada, use o endereço IP da máquina.
    4. Selecione o certificado do cliente. A página **Service Fabric explorer** será exibida.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Configurar a conectividade de LCS do locatário

A implantação e a manutenção do Finance and Operations são orquestradas através de LCS, usando um agente local. Para estabelecer conectividade de LCS ao locatário do Finance and Operations, é necessário configurar um certificado que permite que o agente local atue em nome do locatário do Azure AD (por exemplo, Contoso.Onmicrosoft.com).

Use o certificado do agente local que você obteve de um CA ou o certificado autoassinado que você gerou usando scripts.

Somente as contas de usuário com a função do diretório de Administrador Global podem adicionar certificados para autorizar LCS. Por padrão, a pessoa que assina o Microsoft Office 365 para sua organização será o administrador global do diretório.

> [!NOTE]
> Você deve configurar o certificado exatamente uma vez por locatário. Todos os ambientes locais podem usar o mesmo certificado para se conectarem com o LCS.

1. Baixe e instale a versão mais recente do Azure PowerShell em uma máquina cliente. Para obter mais informações, consulte [Instalar e configurar o Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Conecte-se ao [portal Azure do cliente](https://portal.azure.com) para verificar se você tem a função de diretório de Administração Global.
3. Execute o seguinte script de $(DownloadPath)\\InfrastructureScripts.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Configurar o armazenamento do arquivo

É necessário configurar dois compartilhamentos de arquivo SMB 3.0 altamente disponíveis. Para obter informações sobre como habilitar o SMB 3.0, consulte[Aprimoramentos de Segurança do SMB](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
A negociação de dialeto seguro não pode detectar ou impedir downgrades do SMB 2.0 ou 3.0 para SMB 1.0. Por isso e para aproveitar os recursos completos da criptografia SMB, recomendamos que você desative o servidor SMB 1.0

> [!NOTE]
> Para ajudar a garantir que seus dados estão protegidos enquanto estive em seu ambiente, a Criptografia de Unidade BitLocker deve ser habilitada em cada máquina. Para obter informações sobre como habilitar o BitLocker, consulte [BitLocker: Como implantar no Windows Server 2012 e posterior](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- Um compartilhamento de arquivos que armazena os documentos que são carregados para o AOS (por exemplo, \\\\DAX7SQLAOFILE1\\aos-storage).
- Um compartilhamento de arquivos que armazena a compilação e os arquivos de configuração mais recentes para orquestrar a implantação (por exemplo, \\\\DAX7SQLAOFILE1\\agent)

    > [!NOTE]
    > Mantenha esse caminho de compartilhamento de arquivo o mais curto possível para evitar tamanho máximo de arquivo excedente nos arquivos que serão colocados no compartilhamento.

1. Na máquina de compartilhamento de arquivo, execute o seguinte comando.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Configure o compartilhamento de arquivo \\\\DAX7SQLAOFILE1\\aos-storage

2. No Gerenciador de Servidores, selecione **Serviços de Arquivo e Armazenamento** \> **Compartilhamentos**.
3. Clique em **Tarefas** \> **Novo Compartilhamento** para criar um novo compartilhamento com o nome **aos-storage**.
4. Conceda as permissões **Modificar** para cada máquina no cluster do Service Fabric, exceto **OrchestratorNodeType**.
5. Conceda as permissões **Modificar** para o usuário de domínio do AOS (contoso\\AXServiceUser) e para o usuário do gMSA (contoso\\svc-AXSF).

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Configure o compartilhamento de arquivo do agente \\\\DAX7SQLAOFILE1\\

6. Volte para o Gerenciador de Servidores, selecione **Serviços de Arquivo e Armazenamento** \> **Compartilhamentos**.
7. Clique em **Tarefas** \> **Novo Compartilhamento** para criar um novo compartilhamento com o nome **agent**.
8. Conceda as permissões **Controle total** ao usuário gMSA para o agente de implantação local (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Configurar o SQL Server

1. Instale o SQL Server 2016 SP1 com disponibilidade alta, como clusters de SQL que têm uma configuração de SAN (Storage Area Network) ou Always-On.  Verifique se o **Mecanismo do Banco de Dados, Reporting Services ou Pesquisa de Texto Completo** e as **Ferramentas de Gerenciamento** já estão instaladas.
> [!NOTE]
> Certifique-se de que o SQL Always On está configurado de acordo com [Selecionar Página Inicial de Sincronização de Dados (Assistentes do Grupo de Disponibilidade do Always On)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards) e siga [Preparar Bancos de Dados Secundários Manualmente](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Execute o serviço SQL como um usuário de domínio.
3. Obtenha um certificado SSL de um CA para configurar o Finance and Operations. Para fins de teste, você pode criar e usar um certificado autoassinado.

**Certificado autoassinado para a instância SQL clusterizada**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Certificado autoassinado para a instância SQL Always-On**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. Usando o certificado, conclua as etapas em [Como habilitar a criptografia SSL para uma instância do SQL Server usando a Console de Gerenciamento Microsoft](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) para configurar o SSL no SQL Server.
5. Para cada nó do cluster, rastreie estas etapas. Verifique se fez alterações no nó não ativo e faça failover nele, depois que as alterações forem feitas.

    1. Importe o certificado para LocalMachine\\My.
    2. Conceda as permissões do certificado para a conta de serviço que é usada para executar o SQL service. No Console de Gerenciamento Microsoft (MMC), clique com o botão direito no certificado (certlm.msc) e clique em **Tarefas** \> **Gerenciar chaves particulares**.
    3. Adicione a impressão digital do certificado ao certificado HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\.
    4. No Gerenciador de Configuração do Microsoft SQL Server, defina **ForceEncryption** como **Sim**.

6. Exporte a chave pública do certificado (o arquivo .cer) e instale-o na raiz confiável de cada nó do Service Fabric.

### <a name="configure-the-orchestratordata-database"></a>Configurar o banco de dados OrchestratorData

1.  Crie um base de dados vazio, e nomeie-o **OrchestratorData**. Este banco de dados é usado pelo agente local para orquestrar implantações.
2.  Conceda as permissões de agente local gMSA (svc-LocalAgent$) **db\_owner** no banco de dados:

    1. Na árvore, expanda o nome do servidor, expanda **Segurança** \> **Logons** e clique com o botão direito em **Novo logon**.

        ![Novo comando de logon](./media/OPSetup_01_NewLogin.png)


    2. Pesquise a conta de serviço **svc-LocalAgent$**. Clique em **Locais** e selecione **Diretório Inteiro** e clique em **Tipos de Objetos** e selecione **Conta de Serviço**.

        ![Marque a caixa de diálogo Usuário, Conta de Serviço ou Grupo](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. Defina **Atribuir ServerRole** como **Público**.
    4. Atribua a permissão da função do banco de dados **db\_owner** ao banco de dados OrchestratorData.

### <a name="configure-the-finance-and-operations-database"></a>Configurar o banco de dados do Finance and Operations

1. Entre no LCS (<https://lcs.dynamics.com/v2>).
2. No painel, clique no bloco **Biblioteca de ativos compartilhados**.
3. Clique na guia **Modelo** 
4. Na grade, clique na linha **Dynamics 365 for Operations on-premises, edição Enterprise - Dados de demonstração** para baixar o zip.
5. O arquivo zip contém arquivos vazios e de dados de demonstração .bak. Com base nas suas necessidades selecione o arquivo .bak apropriado. Por exemplo, se precisar de dados de demonstração, restaure o arquivo AxBootstrapDB_Demodata.bak. 
6. Restaure o banco de dados AxBootstrapDB_DemoData.bak.
7. Renomeie o banco de dados **AXDBRAIN**.
8. Execute as seguintes consultas no banco de dados restaurado.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Atualize os arquivos do banco de dados:

    1. Clique com o botão direito no banco de dados e, em seguida, clique em **Propriedades**.
    2. Clique em **Arquivos** para alterar as propriedades do arquivo do banco de dados.
    3. No campo **Tamanho inicial (MB)**, insira um valor que seja maior que 5.120.

        ![Caixa de diálogo propriedades do banco de dados](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. Para **AXDBBuild\_Data**, defina o campo **Autogrowth/Maximize** como **200** megabytes (MB).
    5. Para **AXDBBuild\_Log**, defina o campo **Autogrowth/Maximize** como **500** MB.

        ![Alterar a caixa de diálogo Aumento automático](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Criar um novo usuário com a autenticação de SQL habilitada (axdbadmin).
6. Use as informações da seguinte tabela para mapear as funções de usuários e banco de dados.

    | Usuário             | Tipo    | Função de banco de dados |
    |------------------|---------|---------------|
    | svc-AXSF$        | gMSA    | db\_owner     |
    | svc-LocalAgent$  | gMSA    | db\_owner     |
    | svc-FRPS$        | gMSA    | db\_owner     |
    | svc-FRAS$        | gMSA    | db\_owner     |
    | axdbadmin        | SqlUser | db\_owner     |

7. Forneça ao usuário svc-AXSF$ e ao usuário SQL axdbadmin acesso às seguintes funções no banco de dados tempdb:

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. No Management Studio, execute os seguintes comandos Transact SQL (T-SQL):

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Execute o seguinte comando:
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>Configurar o banco de dados no Financial Reporting

1.  Crie um banco de dados vazio e nomeie-o como **FinancialReporting**.
2.  Use as informações da seguinte tabela para mapear as funções de usuários e banco de dados.

    | Usuário             | Tipo | Função de banco de dados |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_owner     |
    | svc-FRPS$        | gMSA | db\_owner     |
    | svc-FRAS$        | gMSA | db\_owner     |

### <a name="encrypt-credentials"></a>Criptografar credenciais

1. Em qualquer máquina cliente, instale o certificado de codificação no armazenamento LocalMachine\\My certificate.
2. Conceda o acesso de leitura do usuário atual à chave privada deste certificado.
3. Crie o arquivo Credentials.json como mostrado aqui.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** é a senha de usuário de domínio criptografada para o usuário do domínio do AOS (contoso\\axserviceuser).
    - **SqlUser** é o usuário SQL criptografado (axdbadmin) que tem acesso ao banco de dados do Finance and Operations (AXDBRAIN), e **SqlPassword** é a senha SQL criptografada.

4. Copie o arquivo .json para o compartilhamento de arquivos do SMB, \\\\AX7SQLAOFILE1\\agent\\Credentials\\Credentials.json.
5. Atualize o arquivo Credentials.json com os valores criptografados.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. No Credentials.json, substitua **\<encryptedDomainUserPassword\>** pela senha de domínio criptografada.
    2. Substitua **\<encryptedSqlUser\>** pelo usuário SQL do Finance and Operations criptografado.
    3. Substitua **\<encryptedSqlPassword\>** pela senha SQL do Finance and Operations.
    
### <a name="set-up-ssrs"></a>Configurar SSRS

1.  Antes de começar, verifique se os pré-requisitos listados no início deste tópico foram instalados.
2.  Siga as etapas para [Configurar o SQL Server Reporting Services para uma implantação local](../analytics/configure-ssrs-on-premises.md).

### <a name="configure-ad-fs"></a>Configurar AD FS

Antes de concluir este procedimento, o AD FS deve ser implantado no Windows Server 2016. Para obter informações sobre como implantar o AD FS, consulte o [Guia de Implantação do Windows Server 2016 e Guia de Implantação do AD FS 2012 R2](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

O Finance and Operations exige configuração adicional além da configuração pronta para uso padrão do AD FS. Para as seguintes etapas, o Windows PowerShell é executado em uma máquina que tem o serviço da função AD FS instalado. A conta de usuário deverá ter permissões suficientes para administrar o AD FS. Por exemplo, o usuário deve ter uma conta de administrador de domínio.

1. Configure o identificador de AD FS, de forma que ele corresponda ao emissor de token de AD FS.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Você deve desabilitar a Autenticação Integrada do Windows (WIA) para conexões de autenticação intranet, a menos que tenha configurado o AD FS para ambientes mistos. Para obter mais informações sobre como configurar a WIA para que possa ser usada com o AD FS, consulte [Configurar navegadores para usar a WIA (Autenticação Integrada do Windows) com o AD FS](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. Para entrar, o endereço de email do usuário deve ser uma entrada de autenticação aceitável.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

Para que o AD FS confie no Finance and Operations para a troca de autenticação, várias entradas do aplicativo devem ser registradas no AD FS em um grupo de aplicativos AD FS. Para acelerar o processo de configuração e ajudar a reduzir erros, você pode usar o seguinte script para registro. Copie o script Publish-ADFSApplicationGroup.ps1 e o diretório D365FO-OP para uma máquina que tenha o serviço da função AD FS instalado. Em seguida, execute o script usando uma conta de usuário, como uma conta de administrador, que tenha permissões suficientes para administrar AD FS. Para obter mais informações sobre como usar o script, consulte a documentação listada no script. Anote as IDs do cliente que são especificadas na saída, pois essas informações serão solicitadas no LCS posteriormente.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

O console de gerenciamento do AD FS deve ser semelhante à seguinte ilustração. Para abrir o Gerenciador de Servidor, clique em **Ferramentas** \> **Gerenciamento de AD FS** e, em seguida, na parte inferior da exibição em árvore, à esquerda, clique em **Grupos de Aplicativos**. Clique duas vezes no grupo de aplicativos para exibir mais detalhes.

![Propriedades do grupo de aplicativos](./media/OPSetup_05_ApplicatioGroupProperties.png)

Por fim, para obter uma verificação de integridade, certifique-se de que você pode acessar o URL de Configuração OpenID de AD FS em um nó do Service Fabric do tipo **AOSNodeType** indo para `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` em um navegador da Web. Se você receber uma mensagem que declara que o site não é seguro, você não adicionou seu certificado SSL de AD FS ao armazenamento de Autoridades de certificação raiz confiáveis. Esta etapa será descrita na guia de implementação de AD FS. Se você acessar com êxito a URL, um arquivo JSON será retornado que contém a configuração de AD FS, e você verá que a URL de AD FS é confiável.

Com isso a configuração da infraestrutura está concluída. As seções a seguir descrevem como navegar no [LCS](https://lcs.dynamics.com) para configurar seu conector e implantar seu ambiente do Dynamics 365 for Finance and Operations.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Configurar o conector e instalar o agente de local

1. Entre no [LCS](https://lcs.dynamics.com/) e abra o projeto de implementação local.
2. No menu de Hamburger, clique em **Configurações do projeto**.

    ![Comando configurações do projeto](./media/OPSetup_06_ProjectSettings.png)

3. Clique em **Conectores locais**.
4. Clique em **Adicionar** para criar um novo conector.
5. Na guia **Configurar infraestrutura do host**, baixe o instalador do agente.

    ![Botão Baixar o instalador do agente na guia Configurar infraestrutura do host](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Verificar se o arquivo zip está desbloqueado. Clique com o botão direito do mouse no arquivo, clique em **Propriedades** e selecione **Desbloquear**.
7. Descompacte o instalador do agente em um dos nós do Service fabric do tipo **OrchestratorType**.
8. Na guia **Configurar o agente**, insira os parâmetros de configuração.
9. Salve a configuração e clique em **Baixar configurações** para baixar o arquivo de configuração localagent-config.json.

    ![Botão Baixar configurações no guia Configurar agente](./media/OPSetup_08_DownloadConfigurations.png)

10. Copie o arquivo localagent-config.json para a máquina na qual o pacote do instalador do agente está localizada.
11. Na janela Prompt de comando, execute o seguinte comando navegando na pasta que contém o instalador do agente.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > O usuário que está executando esse comando deve ter permissões **db\_owner** no banco de dados OrchestratorData.
    
12. Depois que o agente local for instalado com êxito, navegue novamente para seu conector local no LCS.
13. Na guia **Validar configuração** clique no botão **Agente de mensagem**. Isso testará a conectividade de LCS para seu agente local. Quando a conexão for estabelecida com êxito, a página parecerá com o gráfico abaixo.

     ![Valide o agente](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Implantar o ambiente do Dynamics 365 for Finance and Operations (local)

1. Navegue até o projeto local no LCS, vá para **Ambiente**, **Área restrita** e clique em **Configurar**
2. Selecione a **Topologia de ambiente** e siga o assistente para iniciar sua implantação.
3. O agente local selecionará a solicitação de implantação, abrirá a implantação e comunicará novamente ao LCS quando estiver pronto.

