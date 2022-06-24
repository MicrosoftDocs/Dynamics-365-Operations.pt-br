---
title: Implantação em massa dos componentes de autoatendimento do Commerce lacrados
description: Este artigo explica como usar a estrutura para instaladores de componentes de autoatendimento para instalar e fazer implantações silenciosas de serviço.
author: jashanno
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: a679d78db3ad5bd9cccbd4ab6a7026bd07890f55
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898570"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Implantação em massa dos componentes de autoatendimento do Commerce lacrados

[!include [banner](../includes/banner.md)]

Este artigo se aplica à estrutura lacrada, instaladores de componentes que são lançados todos os meses, começando com a versão 10.0.18, e que são disponibilizados na biblioteca de ativos compartilhados nos Microsoft Dynamics Lifecycle Services (LCS). Observe que as primeiras versões destes novos instaladores são designadas como **(Versão preliminar)**. No entanto, o único propósito desta designação é diferenciar os novos instaladores, enquanto a Microsoft determina se há requisitos funcionais adicionais para usá-los. Isso não significa que os instaladores não são válidos para a produção. Com base no lançamento desses novos instaladores, a Microsoft planeja preterir os antigos instaladores (legados) em ou por volta de outubro de 2023. 

Este artigo explica como usar os novos instaladores para executar atualizações silenciosas de instalação e manutenção usando argumentos da linha de comando. Esses argumentos permitem que você faça a implantação em massa de várias maneiras diferentes.

> [!NOTE]
> Os novos instaladores selados e de autoatendimento não serão disponibilizados no headquarters e só poderão ser baixados no LCS.

## <a name="delimiters-for-mass-deployment"></a>Delimitadores para implantação em massa

A tabela a seguir mostra os delimitadores que podem ser usados na execução da linha de comando.


| Delimitador                 | Descrição |
|---------------------------|-------------|
| --AadTokenIssuerPrefix | O prefixo para o emissor de tokens da Microsoft Azure Active Directory (Azure AD). |
| --AsyncClientAadClientId | O ID do cliente Azure AD que o Cliente Async deve usar durante as comunicações com o headquarters. |
| --AsyncClientAppInsightsInstrumentationKey | Chave de instrumentação do Async Client AppInsights. |
| --AsyncClientCertFullPath | O caminho URN totalmente formatado que usa a impressão digital como a métrica de pesquisa do local de certificado do Async Client Identity que deve ser usado para autenticar com o Azure AD para comunicações com o headquarters. Por exemplo, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` é um URN de formato correto. O valor **\<MyThumbprint\>** será substituído pela impressão digital do certificado que deve ser usada. Não use este parâmetro junto com o parâmetro **-AsyncClientCertThumbprint**. |
| --AsyncClientCertThumbprint | A impressão digital do certificado do Async Client Identity que deve ser usado para autenticar com Azure AD para comunicações com o headquarters. Essa impressão digital será usada para pesquisar na localização e nome da **LocalMachine/My store** para encontrar o certificado correto a ser usado. Não use este parâmetro junto com o parâmetro **-AsyncClientCertFullPath**. |
| --ClientAppInsightsInstrumentationKey | Chave de instrumentação do Client AppInsights. |
| --CloudPosAppInsightsInstrumentationKey | Chave de instrumentação do Cloud POS AppInsights. |
| --Config | O arquivo de configuração que deve ser usado durante a instalação. Um exemplo de nome de arquivo é **Contoso.CommerceScaleUnit.xml**. |
| --CposAadClientId | O ID do cliente Azure AD que o Cloud POS deve usar durante a ativação do dispositivo. Este parâmetro não é necessário para implantações no local. |
| --Device | O ID do dispositivo, como mostrado na página **Dispositivos** no headquarters. |
| --EnvironmentId | ID do ambiente. |
| --HardwareStationAppInsightsInstrumentationKey | Chave de instrumentação AppInsights da estação do hardware. |
| --Install | Um parâmetro que especifica se o componente que este instalador fornece deve ser instalado. Este parâmetro não é obrigatório. |
| --InstallOffline | Para Modern POS, este parâmetro especifica que o banco de dados offline também deve ser instalado e configurado. Use o parâmetro **-SQLServerName** também. Caso contrário, o instalador tentará encontrar uma instância padrão que atenda aos pré-requisitos. |
| --Port | A porta que deve ser associada e usada pelo diretório virtual do Retail Server. Se nenhuma porta for definida, a porta padrão, 443, será utilizada. |
| --Register | O ID do registro, como mostrado na página **Registros** no headquarters. |
| --RetailServerAadClientId | O ID do cliente Azure AD que o Retail Server deve usar durante as comunicações com o headquarters. |
| --RetailServerAadResourceId | O ID de recurso do aplicativo Retail Server Azure AD que deve ser usado durante a ativação do dispositivo. Este parâmetro não é necessário para implantações no local. |
| --RetailServerCertFullPath | O caminho URN totalmente formatado que usa a impressão digital como a métrica de pesquisa do local de certificado do Retail Server Identity que deve ser usado para autenticar com o Azure AD para comunicações com o headquarters. Por exemplo, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` é um URN de formato correto onde o valor **\<MyThumbprint\>** será substituído pela impressão digital do certificado que deve ser usada. Não use este parâmetro junto com o parâmetro **-RetailServerCertThumbprint**. |
| --RetailServerCertThumbprint | A impressão digital do certificado do Retail Server Identity que deve ser usado para autenticar com Azure AD para comunicações com o headquarters. Essa impressão digital será usada para pesquisar na localização e nome da **LocalMachine/My store** para encontrar o certificado correto a ser usado. Não use este parâmetro junto com o parâmetro **-RetailServerCertFullPath**. |
| --RetailServerURL | A URL do Retail Server que o instalador deve usar. (Esta URL também é conhecida como URL do \[CSU\] (Commerce Scale Unit).) Para o Modern POS, esse valor será usado durante a ativação do dispositivo. |
| --SkipAadCredentialsCheck| Uma opção que indica se as verificações de pré-requisitos de credencial do Azure AD devem ser ignoradas. O valor padrão é **false**. |
| --SkipCertCheck | Uma opção que indica se as verificações de pré-requisitos de certificado devem ser ignoradas. O valor padrão é **false**. |
| --SkipIisCheck | Uma opção que indica se as verificações de pré-requisitos de Serviços de Informações da Internet (IIS) devem ser ignoradas. O valor padrão é **false**. |
| --SkipNetFrameworkCheck | Uma opção que indica se as verificações de pré-requisitos do .NET Framework devem ser ignoradas. O valor padrão é **false**. |
| --SkipScaleUnitHealthcheck | Uma opção que indica se a verificação de integridade nos componentes instalados deve ser ignorada. O valor padrão é **false**. |
| --SkipSChannelCheck | Uma opção que indica se as verificações de pré-requisitos do canal seguro devem ser ignoradas. O valor padrão é **false**. |
| --SkipSqlFullTextCheck | Uma opção que indica se a validação do pré-requisito do SQL Server que requer a Pesquisa de Texto Completo deve ser ignorada. O valor padrão é **false**. |
| --SkipSqlServerCheck | Uma opção que indica se as verificações de pré-requisitos de SQL Server devem ser ignoradas. O valor padrão é **false**. |
| --SqlServerName | Nome do SQL Server. Se o nome não for especificado, o instalador tentará encontrar a instância padrão. |
| --SslcertFullPath | O caminho do URN totalmente formatado que usa a impressão digital como a métrica de pesquisa do local do certificado que deve ser usado para criptografar o tráfego HTTP para a unidade de escala. Por exemplo, `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` é um URN de formato correto onde o valor **\<MyThumbprint\>** será substituído pela impressão digital do certificado que deve ser usada. Não use este parâmetro junto com o parâmetro **-SslCertThumbprint**. |
| --SslCertThumbprint | A impressão digital do certificado que deve ser usado para criptografar o tráfego HTTP para a unidade de escala. Essa impressão digital será usada para pesquisar na localização e nome da **LocalMachine/My store** para encontrar o certificado correto a ser usado. Não use este parâmetro junto com o parâmetro **-SslCertFullPath**. |
| --StoreSystemAosUrl | URL (Microsoft Dynamics AX Application Object Server (AOS)) do headquarters. |
| --StoreSystemChannelDatabaseId | ID do banco de dados de canal (nome). |
| --TenantId | ID de locatário do Azure AD. |
| --TransactionServiceAzureAuthority | Autoridade do Transaction Service Azure AD. |
| --TransactionServiceAzureResource | Recurso do Transaction Service Azure AD. |
| --TrustSqlServerCertificate | Uma opção que indica se o certificado de servidor deve ser confiável enquanto uma conexão com o SQL Server está sendo estabelecida. Para ajudar a evitar riscos de segurança, as implantações de produção nunca devem fornecer um valor **verdadeiro** aqui. O valor padrão é **false**. |
| --Verbosity | Nível de registro solicitado durante a instalação. Normalmente, esse valor não deve ser usado. |
| --WindowsPhoneAppInsightsInstrumentationKey | Chave de instrumentação AppInsights da estação do hardware. |

## <a name="general-overview"></a>Visão geral

A nova estrutura para instaladores de autoatendimento tem vários recursos e melhorias. A nova estrutura atualmente gera instaladores apenas para Modern POS, estação de hardware e CSU (auto-hospedado). É importante entender o uso básico da linha de comando dos instaladores lacrados, que devem ser semelhantes aos utilizados no exemplo a seguir. 
 
```Console
<Component Installer Name>.exe install --<Parameter Name> "<Parameter Information>"
```

O instalador requer a **instalação** do parâmetro (ou **desinstalação** para remover a instalação) e quaisquer parâmetros específicos dessa instalação. O **Nome do Parâmetro** deve incluir quaisquer parâmetros necessários, como informações de registro, URL do CSU ou certificado. As **Informações do Parâmetro** devem incluir qualquer informação adicional sobre os parâmetros.

A estrutura selada foi criada para permitir as seguintes alterações:
- **Selado** – A nova estrutura do instalador separa completamente os instaladores de componentes de base distribuídos pela Microsoft das personalizações baseadas em extensibilidade. As personalizações serão instaladas posteriormente, mas serão desativadas em relação às atualizações (de modo que as atualizações serão permitidas apenas para o componente de base da Microsoft, apenas para as personalizações ou para ambos).
- **Sem GUI** – Não há mais interface de usuário (IU). Em vez disso, há uma linha de comando totalmente executável para cada instalador de componentes. Essa alteração é uma das várias mudanças ou recursos importantes que são usados para direcionar a nova estrutura do instalador para uso com implantação em massa.
- **Registro avançado** – Os registros avançados do instalador permitem uma melhor validação da conclusão ou falha da instalação, das etapas que foram executadas e dos avisos ou erros gerados.
- **Limpeza** – Na nova estrutura, os instaladores de componentes trabalham mais para manter a limpeza dos diretórios de instalação, removendo o conteúdo completo da pasta de componentes antes de instalar os componentes mais novos. Essa limpeza garante que não haja arquivos que possam causar problemas e atrapalhar uma instalação bem-sucedida.

Três componentes não foram migrados para a nova estrutura: o Simulador Periférico Virtual, o Async Server Connector service (usado para suporte ao Dynamics AX 2012 R3) e o Real-time Service Replacement (usado para suporte ao Dynamics AX 2012 R3).

> [!NOTE]
> Os instaladores são armazenados localmente e mantidos.  É importante gerenciar ou excluir os instaladores salvos para não desperdiçar espaço em disco. Recomenda-se manter o instalador atual para os componentes de base e quaisquer instaladores de extensão para as versões mais recentes no caso de recuperação de situações extremas.

## <a name="migration"></a>Migração

A migração dos antigos instaladores de componentes de estrutura de autoatendimento para os novos instaladores de componentes de estrutura requer a desinstalação dos componentes antigos.

- **Modern POS** – A nova estrutura do instalador fez com que o aplicativo recebesse um novo ID de assinatura de aplicativo. Portanto, é necessária a desinstalação total de componentes antigos antes que o novo componente Modern POS da estrutura seja instalado. Devido à exigência de desinstalação total, será necessário ativar o dispositivo novamente. (A reativação deste dispositivo é um requisito único, desde que a desinstalação não ocorra novamente.)
- **Estação de hardware** – Como um site do IIS, a nova estrutura do instalador exige que a estrutura da pasta base seja reformulada. Portanto, é necessária a desinstalação total de componentes antigos antes que o novo componente de estação de hardware da estrutura seja instalado.
- **Commerce Scale Unit (CSU, auto-hospedada)** – Como uma série de sites do IIS, a nova estrutura do instalador exige que a estrutura da pasta base seja reformulada.  Portanto, é necessária a desinstalação total de componentes antigos antes que o novo componente CSU (auto-hospedada) da estrutura seja instalado.

## <a name="modern-pos"></a>Modern POS

### <a name="before-you-begin"></a>Antes de começar

É fundamental que você remova o antigo componente Modern POS de autoatendimento. Para obter mais informações, consulte as etapas de migração anteriormente neste artigo.

### <a name="examples-of-silent-deployment"></a>Exemplos de implantação silenciosa

Esta seção mostra exemplos de comandos que são usados para instalar o Modern POS.

#### <a name="silently-install-modern-pos"></a>Instalar o Modern POS de forma silenciosa

O comando a seguir instala silenciosamente (ou atualiza) Modern POS. Possui a estrutura de comando padrão que é usada para manutenção silenciosa de componentes que estão atualmente instalados. A estrutura utiliza os valores básicos do **&lt;InstallerName&gt;.exe**.

O seguinte comando básico mostra as opções disponíveis se uma instalação for solicitada. É altamente recomendável que este comando seja usado no primeiro teste ou uso do instalador.

```Console
CommerceModernPOS.exe --help install
```

> [!NOTE]
> Um arquivo de configuração não é necessário para Modern POS. O instalador agora tem parâmetros (mostrados anteriormente neste artigo) para os vários valores que são usados durante a ativação do dispositivo.

O comando a seguir especifica todos os parâmetros que devem ser usados durante a ativação do dispositivo após a instalação do aplicativo Modern POS. Este exemplo usa o registro **Houston-3**, que é um valor comumente usado em dados de demonstração do Dynamics 365 Commerce.

```Console
CommerceModernPOS.exe install --Register "Houston-3" --Device "Houston-3" --RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

O comando a seguir especifica os parâmetros que devem ser usados para instalar e configurar o banco de dados offline. O SQL Server é especificado juntamente com o arquivo de configuração que deve ser utilizado.

```Console
CommerceModernPOS.exe install --InstallOffline --SQLServerName "SQLExpress" --Config "ModernPOS.Houston-3.xml"
```

Você pode misturar e combinar esses conceitos para alcançar os resultados de instalação que você deseja.

## <a name="hardware-station"></a>Estação de hardware

### <a name="before-you-begin"></a>Antes de começar

É fundamental que você remova o antigo componente da estação de hardware de autoatendimento. Para obter mais informações, consulte as etapas de migração anteriormente neste artigo. Não existe mais uma Ferramenta de Informações de Contas do Comerciante. Em vez disso, as informações da conta do comerciante são instaladas quando um terminal de PDV é emparelhado com a estação de hardware. Ao testar esse instalador pela primeira vez, é altamente recomendável que você execute o seguinte comando:

```Console
CommerceHardwareStation.exe --help install
```

### <a name="examples-of-silent-deployment"></a>Exemplos de implantação silenciosa

Esta seção mostra exemplos de comandos que são usados para instalar a estação de hardware.

#### <a name="silently-install-hardware-station"></a>Instalar silenciosamente a estação de hardware

O comando a seguir instala silenciosamente (ou atualiza) a estação de hardware. Possui a estrutura de comando padrão que é usada para manutenção de componentes que estão atualmente instalados. A estrutura utiliza os valores básicos do **&lt;InstallerName&gt;.exe**.

O seguinte comando básico executa o instalador de arquivos executável.

```Console
HardwareStation.exe install --Port 443 --StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" --StoreSystemChannelDatabaseID "Houston" --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> Um arquivo de configuração não é necessário para a estação de hardware. O instalador agora tem parâmetros (mostrados anteriormente neste artigo) para os vários valores que são necessários.

O comando a seguir especifica todos os parâmetros necessários para ignorar as verificações de pré-requisitos durante uma instalação padrão. 

> [!NOTE]
> Pular verificações não é recomendado sem testes minuciosos antes do tempo ou em situações de desenvolvimento.

```Console
HardwareStation.exe install --SkipFirewallUpdate --SkipOPOSCheck --SkipVersionCheck --SkipURLCheck --Config "HardwareStation.Houston.xml"
```

Como de praxe, é comum misturar e combinar esses conceitos para alcançar os resultados de instalação que você deseja.

## <a name="commerce-scale-unit-self-hosted"></a>Commerce Scale Unit (auto-hospedada)

Ao testar esse instalador pela primeira vez, é altamente recomendável que você execute o seguinte comando:

```Console
CommerceStoreScaleUnitSetup.exe --help install
```

### <a name="before-you-begin"></a>Antes de começar

É fundamental que você remova o antigo componente CSU de autoatendimento (auto-hospedado). Para obter mais informações, consulte as etapas de migração anteriormente neste artigo.

### <a name="examples-of-silent-deployment"></a>Exemplos de implantação silenciosa

Esta seção mostra exemplos de comandos que são usados para instalar o CSU (auto-hospedado).

#### <a name="silently-install-csu-self-hosted"></a>Instalar silenciosamente o CSU (auto-hospedado)

O comando a seguir instala silenciosamente (ou atualiza) CSU (auto-hospedado). Possui a estrutura de comando padrão que é usada para manutenção silenciosa de componentes que estão atualmente instalados. A estrutura utiliza os valores básicos do **&lt;InstallerName&gt;.exe**.

Em comparação com os outros instaladores de autoatendimento, o Commerce Scale Unit (CSU) é mais complexo e requer uma quantidade bastante grande de informações adicionais. O seguinte comando é o comando mínimo (com parâmetros) necessário para executar o instalador de arquivo executável quando nenhum arquivo de configuração estiver presente.

```Console
CommerceScaleUnit.exe install --port 446 --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> Um arquivo de configuração ainda é necessário para o CSU (auto-hospedado).

O comando a seguir é um comando mais completo que executa o instalador de arquivos executável com alguns parâmetros alternativos.

```Console
CommerceScaleUnit.exe install --Port 446 --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Verbosity 0 --Config "Contoso.StoreSystemSetup.xml"
```

O comando a seguir especifica os parâmetros necessários para ignorar as verificações de pré-requisitos durante uma instalação padrão. 

> [!NOTE]
> Pular verificações não é recomendado sem testes minuciosos antes do tempo ou em situações de desenvolvimento.


```Console
CommerceScaleUnit.exe installer --skipscaleunithealthcheck --skipcertcheck --skipaadcredentialscheck --skipschannelcheck --skipiischeck --skipnetcorebundlecheck --skipsqlservercheck --skipnetframeworkcheck --skipversioncheck --skipurlcheck --Config "Contoso.StoreSystemSetup.xml" --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate
```

Você pode misturar e combinar esses conceitos para alcançar os resultados de instalação que você deseja.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
