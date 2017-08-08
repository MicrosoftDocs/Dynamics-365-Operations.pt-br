---
title: Requisitos do sistema
description: "Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise para as implantações de nuvem e locais."
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: pt-br
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Requisitos do sistema

[!include[banner](../includes/banner.md)]


Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise para as implantações de nuvem e locais. Antes de instalar o Finance and Operations, quando necessário, verifique se o sistema que você está trabalhando atende ou excede os requisitos mínimos de rede, hardware e de software.


## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office suportados
Os seguintes aplicativos do Office são suportados nas implantações de nuvem e locais do Finance and Operations.
-   Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para obter mais detalhes sobre os requisitos de versão, consulte [Solução de problemas de integração Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para exibir documentos que são gerados pela exportação para Excel ou exportar para funcionalidade do Word, você deve ter o Microsoft Office 2007 ou posterior instalado.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Requisitos específicos do sistema para implantações em nuvem
## <a name="network-requirements"></a>Requisitos de rede
-   O Finance and Operations é projetado para redes com latência de 250 a 300 milissegundos (ms) ou menos. Esta é a latência de um cliente de navegador para o centro de dados Microsoft Azure que hospeda Dynamics 365 for Finance and Operations. Recomendamos que teste a latência da rede em <http://www.azurespeed.com>.
-   Os requisitos de largura do Finance and Operations dependem de seu cenário. A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps). No entanto, para cenários com requisitos de carga útil elevados, como espaços de trabalho ou cenários que envolvem personalização extensiva, recomenda-se mais largura de banda.

Em geral, o Finanças e Operações é otimizado para a Internet. O número de viagens de ida e volta de um cliente de navegador para o centro de dados do Azure é muito pequeno e toda a carga útil é compactada. 

> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de visualização do Finanças e Operações.

## <a name="net-framework-requirements"></a>Requisitos do .NET Framework
O Finance and Operations requer a versão 4.6.2 do .NET Framework para aplicativos de clique único, como o agente de roteiro do documento. Para obter instruções de instalação, consulte [Instalando o .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Navegadores da web suportados
O aplicativo de web pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:


-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10
-   Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad

Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software. 

> [!NOTE]
> -   Uma extensão do Chrome de pré-lançamento deve ser instalada para permitir que as capturas de tela sejam capturadas pelo Task Recorder e incluídas em documentos do Microsoft Word gerados. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce. Somente o Microsoft Edge e o Internet Explorer (em uma versão com suporte do Microsoft Windows) suportam aplicativos ClickOnce. O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.
> -   O Report Designer for Financial Reporting é iniciado como um aplicativo ClickOnce. Ele requer um sistema operacional compatível com 64 bits. Se estiver usando o Chrome, instale uma extensão ClickOnce para baixar o cliente de designer de relatórios. Se estiver usando o Chrome com o modo de navegação anônima, verifique se a extensão ClickOnce também está ativada para o modo de navegação anônima.
> -   Para visualizar os arquivos PDF, recomendamos que você use navegadores como Microsoft Edge (última versão liberada publicamente) no Windows 10 ou Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou tablet Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navegadores da web suportados para o Retail Cloud POS

O PDV de nuvem de varejo pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, ou Windows 7

## <a name="retail-modern-pos-requirements"></a>Requisitos modernos de POS de varejo
### <a name="supported-operating-systems"></a>Sistemas operacionais suportados

-   O Retail POS moderno é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.
-   O varejo POS moderno é suportado somente em edições de ramal de serviço de longo prazo Enterprise (LTSB), do Windows 10 Pro, e Enterprise.

### <a name="minimum-system-requirements"></a>Requisitos mínimos do sistema

-   A resolução mínima suportada é 1280 × 1024.
-   O computador em que o Retail Modern POS funciona deve atender a esses requisitos:
    -   Ele deve ter, no mínimo, um processador dual-core que funciona a não menos de 2 gigahertz (GHz).
    -   Ele deve ter, no mínimo, 3 gigabytes (GB) de RAM.
    -   Deve ter acesso à Internet.

## <a name="retail-hardware-station-requirements"></a>Requisitos de estações de hardware de varejo
### <a name="supported-operating-systems"></a>Sistemas operacionais suportados

-   A estação de hardware de varejo é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.
-   A estação de hardware de varejo é suportada nos seguintes sistemas operacionais:
    -   Edições do Windows 7 Professional, Enterprise, e Ultimate 
    
    > [!NOTE]
    > O Windows 7 tem suporte apenas se o Internet Explorer 11 for instalado manualmente no sistema.

    -   Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas
    -   Edições LTSB Enterprise, Windows 10 Pro, e Enterprise

### <a name="minimum-system-requirements"></a>Requisitos mínimos do sistema

O computador deve atender a todos os requisitos do sistema para instalar e usar os seguintes itens:

-   Serviços de Informações da Internet (IIS)
-   Hardware de terceiros

## <a name="retail-store-scale-unit-requirements"></a>Requisitos da unidade de escala de loja de varejo
### <a name="supported-operating-systems"></a>Sistemas operacionais suportados

-   A unidade de escala de loja de varejo é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.
-   A unidade de escala de loja de varejo é suportada nos seguintes sistemas operacionais:
    -   Edições do Windows 7 Professional, Enterprise, e Ultimate
    -   Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas
    -   Edições LTSB Enterprise, Windows 10 Pro, e Enterprise

### <a name="minimum-system-requirements"></a>Requisitos mínimos do sistema

-   4 GB de RAM
-   Velocidade máxima de CPU de 1,6 GHz por núcleo (dois núcleos no mínimo.)
-   Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)

### <a name="recommended-system-requirements"></a>Requisitos de sistema recomendados

-   6 GB de RAM
-   i7 com 2,4 GHz (ou equivalente) de velocidade máxima de CPU por núcleo (são recomendados quatro núcleos.)
-   Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)

## <a name="connector-requirements"></a>Requisitos do conector
### <a name="supported-operating-systems"></a>Sistemas operacionais suportados

-   O conector do Microsoft Dynamics AX tem dois instaladores separados, **Serviço de conector de servidor de Async** e **Serviço de tempo real para Dynamics AX 2012 R3**.
-   Ambos os componentes são aplicativos de 32 bits, mas serão executados em arquiteturas x86 e x64.
-   Os componentes são suportados nos seguintes sistemas operacionais:
    -   Edições do Windows 7 Professional, Enterprise, e Ultimate
    -   Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas
    -   Edições LTSB Enterprise, Windows 10 Pro, e Enterprise
    -   Windows Server 2012 R2, Windows Server 2016

### <a name="minimum-system-requirements"></a>Requisitos mínimos do sistema

-   2 GB de RAM, 4 GB de RAM recomendados
-   Velocidade máxima de CPU de 1,6 GHz por núcleo (dois núcleos no mínimo.)
-   Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)

## <a name="requirements-for-development-on-local-vms"></a>Requisitos do desenvolvimento em VMs locais
Para obter informações sobre os requisitos de desenvolvimento em máquinas virtuais locais (VMs), consulte [VM em execução no local](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Requisitos do sistema para implantações locais

## <a name="network-requirements"></a>Requisitos de rede
O Finance and Operations (local) pode funcionar em redes que usam a versão 4(IPv4) ou a versão 6 (IPv6) do Protocolo da Internet. Considere o ambiente de rede ao planejar seu sistema e use as seguintes diretrizes.

### <a name="network-response-time"></a>Tempo de resposta de rede
A seguinte tabela lista os requisitos mínimos de rede para a conexão entre o navegador da Web e o Servidor de Objetos de Aplicativo (AOS) e para a conexão entre AOS e o banco de dados em um sistema local.

| Alíquota     | Navegador da Web para AOS | AOS para banco de dados                                            |
|-----------|--------------------|------------------------------------------------------------|
| Largura de banda | 50 KBps por usuário   | 100 MBps                                                   |
| Latência   | < 250-300 ms       | < 1 ms (somente LAN). AOS e a necessidade do banco de dados ser localizado. |

- O Finance and Operations (local) é projetado para redes que têm uma latência de 250–300 milissegundos (ms) ou menos. Esta é a latência de um cliente de navegador para o centro de dados que hospeda o Finance and Operations.
- Os requisitos de largura de banda do Finance and Operations (local) dependem de seu cenário. Os cenários típicos exigem uma largura de banda de mais de 50 kilobytes por segundo (KBps) entre o navegador e o servidor do Finance and Operations. No entanto, para cenários com requisitos de carga útil elevados, como espaços de trabalho ou cenários que envolvem personalização extensiva, recomenda-se mais largura de banda e isso depende do uso.
Não são suportadas as implantações nas quais o AOS e o Banco de Dados do SQL Server estão em centros de dados diferentes. O AOS e o banco de dados do SQL Server precisar ser localizados. Geralmente, o Finance and Operations é otimizado para reduzir viagens de ida e volta do navegador para o servidor. O número de viagens de ida e volta de um cliente do navegador para o centro de dados é zero ou um para cada interação do usuário e a carga é compactada.

> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Sugerimos usar uma simulação de real em um ambiente de não produção do Finance and Operations como o melhor indicador de desempenho para seu caso específico. 

### <a name="lan-environments"></a>Ambientes de LAN
Em ambientes de rede local (LAN). o Microsoft Remote Desktop no Microsoft Windows Server não é necessário para conexão ao Finance and Operations. Entretanto, ele pode ser necessário para operações de manutenção nas VMs que compõem as implantações do servidor.

### <a name="wan-environments"></a>Ambientes de WAN
Em ambientes de ampla área de rede (WAN), o Remote Desktop no Windows Server não é necessário para conexão ao Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Requisitos de conectividade da Internet
O Finance and Operations (local) não exige conectividade da Internet das estações de trabalho do usuário final. No entanto, alguns recursos não estarão disponíveis sem conectividade da Internet.

| Cliente de navegador | Um cenário da intranet sem conectividade de Internet é um ponto de design para a opção de implantação local. Alguns recursos que exigem serviço de nuvem não estarão disponíveis, como bibliotecas de guias de tarefas e Ajuda no LCS. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Servidor         | A camada de AOS ou do Service Fabric deve se comunicar ao LCS. O cliente baseado no navegador local não requer acesso à Internet.                                                                                |
| Telemetria      | Os dados de telemetria poderão ser perdidos, se houver interrupções longas na conectividade. As interrupções na conectividade para LCS não afetam a funcionalidade do aplicativo local.                                                |
| LCS            | A conectividade ao LCS é necessária para implantação, implantação de código e operações de manutenção.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Transferência de dados de telemetria à nuvem
A maioria da telemetria é armazenada localmente e pode ser acessada usando o Visualizador de Eventos no Microsoft Windows. Um pequeno subconjunto de telemetria é transferido para o pipeline de telemetria do Microsoft na nuvem de diagnóstico. Os dados do cliente e os dados do usuário final identificáveis não fazem parte da telemetria enviada à Microsoft. Os nomes da VM são enviados à Microsoft para ajudar no gerenciamento e diagnóstico do ambiente do portal de LCS.

## <a name="domain-requirements"></a>Requisitos de domínio
Considere os seguintes requisitos de domínio ao instalar o Finance and Operations (local):

- As máquinas virtuais que hospedam os componentes do Finance and Operations (local) devem pertencer a um domínio do Active Directory. Os serviços de domínio do Active Directory (AD DS) devem ser configurados no modo nativo.
- As máquinas virtuais que executam os componentes do Finance and Operations (local) devem ter acesso a cada uma configurada nos Serviços de Domínio do Active Directory. 
- O controlador de domínio deve ser executado no Microsoft Windows Server 2016.

## <a name="hardware-requirements"></a>Requisitos de hardware
Esta seção descreve o hardware necessário executar o Finance and Operations (local).
Com base na configuração do sistema, composição de dados e aplicativos e recursos que você decide usar, os requisitos de hardware reais irão variar. Aqui estão alguns dos fatores que podem afetar a escolha de hardware apropriado para Finance and Operations (local):

- O número de transações por hora.
- O número de usuários simultâneos.

## <a name="minimum-infrastructure-requirements"></a>Requisitos mínimos de infraestrutura
O Finance and Operations (local) usa o Service Fabric do Microsoft Azure para hospedar os serviços de AOS, Lote, Gerenciamento de dados, Management reporter e orquestrador no ambiente. O Microsoft SQL Server Reporting Services (SSRS) não está hospedados no cluster do Service Fabric.
O SQL Server deve ser definido em uma configuração HADRON de alta disponibilidade que tenha pelo menos dois nós para uso em produção.
A figura a seguir mostra o número mínimo recomendado de nós no cluster do Service Fabric.

[![número recomendado de nós para cluster do service fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Requisitos do Processador e de RAM
A tabela a seguir lista o número de processadores e o valor de memória RAM necessário para cada uma das funções necessárias para executar esta opção de implantação. Para obter mais informações, leia a recomendação de requisitos mínimos do cluster autônomo do Service Fabric, [Planejar e preparar seu cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Se outro software da Microsoft for instalado no mesmo computador, o sistema também deve estar de acordo com os requisitos de hardware de tal software. Recomendamos limitar outros aplicativos de servidor no mesmo computador que AOS para 1 gigabyte (GB) de RAM.

**Dimensionamento por tipo de funções e de topologia**

| Topologia   | Funções (tipo de nó)              | Núcleos do processador recomendados | Memória recomendada (GB) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Produção | AOS, Gerenciamento de dados, Lote   | 8                           | 24                      |
|            | Management Reporter           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |
| Área restrita    | AOS, Gerenciamento de dados, Lote   | 4                           | 24                      |
|            | Management Reporter           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |

**Previsões mínimas de dimensionamento para implantações de produção e de área restrita**\*

| Topologia                                  | Função                          | Número de instâncias |
|-------------------------------------------|-------------------------------|---------------------|
| Produção                                | AOS (Gerenciamento de dados, Lote)  | 3                   |
|                                           | Management Reporter           | 2                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Orchestrator\*\*                | 3                   |
| Área restrita                                   | AOS, Gerenciamento de dados, Lote   | 2                   |
|                                           | Management Reporter           | 1                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Orchestrator                  | 3                   |
| *Topologias resumidas de Produção e de Área restrita* |                               | 16                  |

\*Esses números estão sendo validados por nossos clientes de visualização e podem ser ajustados, conforme necessário, com base nesse feedback.

\*\*O Orchestrator foi designado como o tipo de nó principal e será usado também para executar os serviços do Service Fabric.

**Estimativas iniciais para o SQL Server e o AD de back-end**

[![Estimativas iniciais para o SQL Server e o AD de back-end](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*Os tamanhos do SQL Server são altamente dependentes das cargas de trabalho. Para obter mais informações, consulte a seção [Dimensionamento de hardware para ambientes locais](#Hardware-sizing-for-on-premises-environments).

## <a name="storage"></a>Armazenamento

- **AOS** - O Finance and Operations (local) usará um compartilhamento de Server Message Block (SMB) 3.0 para armazenar os dados não estruturados. Para obter mais informações, consulte [Espaços de Armazenamento Diretos no Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – Opções viáveis:
    - Uma configuração de unidade de estado sólido (SSD) disponível.
    - Uma rede de área de armazenamento (SAN) otimizada para produtividade de OLTP.
    - Armazenamento de conexão direta (DAS) de alto desempenho 
- **SQL e IOPS de gerenciamento de dados** – O armazenamento para gerenciamento de dados e SQL Server deve ter pelo menos 2.000 operações de entrada/saída por segundo (IOPS). IOPS de produção dependem de muitos fatores. Para obter mais informações, consulte a seção “Dimensionamento de hardware para ambientes locais”. 
- **IOPS da máquina virtual** – Cada máquina virtual deve ter pelo menos 100 IOPS de gravação.

## <a name="virtual-host-requirements"></a>Requisitos do host virtual
Ao configurar hosts virtuais para um ambiente do Finance and Operations (local), consulte as seguintes diretrizes: [Planejar e preparar seu cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) e [Descrevendo um cluster do service fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Host cada virtual deve ter núcleos suficientes para a infraestrutura que está sendo dimensionada. Várias configurações avançadas são possíveis, onde o SQL Server reside no hardware físico, mas todo o resto é virtualizado. Se o SQL Server for virtualizado, o subsistema de disco deve ser uma SAN rápida ou equivalente. Em todos os casos, certifique-se de que a configuração básica do host virtual é altamente disponível e redundante. Em todos os casos, quando a virtualização for usada, nenhum instantâneo de VM deve ser obtido.

## <a name="software-requirements-for-all-server-computers"></a>Requisitos de software todos os computadores do servidor
O seguinte software deve estar presente em um computador antes de quaisquer componentes do Finance and Operations (local) serem instalados:

- Microsoft .NET Framework 4.5.1 ou superior
- Service Fabric Para obter mais informações, consulte [Planejar e preparar seu cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Sistemas operacionais do servidor suportados
A tabela a seguir lista os sistemas operacionais do servidor que são suportados para os componentes do Finance and Operations.

| Sistema operacional                                     | Observação                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Datacenter ou Padrão | Esses requisitos são para o banco de dados e o cluster do Service Fabric que hospeda o AOS. |

## <a name="software-requirements-for-database-servers"></a>Requisitos de software para servidores do banco de dados

- Somente as versões de 64 bits do SQL Server 2016 são suportadas.
- Em um ambiente de produção, recomendamos a instalação da última atualização cumulativa(CU) da versão do SQL Server que você está usando.
- O Finance and Operations (local) suporta agrupamentos que não diferenciam maiúsculas de minúsculas, diferenciam acentos, diferenciam kana, não diferenciam largura. O agrupamento deve corresponder à localidade dos computadores Windows que estão executando instâncias do AOS. Se estiver configurando uma nova instalação, recomendamos que você selecione um agrupamento do Windows, em vez de um agrupamento do SQL Server. Para obter mais informações sobre como selecionar um agrupamento para um banco de dados do SQL Server, consulte [documentação do SQL Server](/sql/sql-server/sql-server-technical-documentation).
A tabela a seguir lista as versões do SQL Server que são suportadas para os bancos de dados do Finance and Operations. Para obter mais informações, consulte os requisitos mínimos de hardware para [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Necessidade                                                      | Observação                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition ou Enterprise Edition | Para os requisitos de hardware do SQL Server 2016, consulte [Requisitos de hardware e o software para instalar SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>Requisitos de software todos os computadores do cliente
O aplicativo da Web do Finance and Operations pode ser executado em qualquer dispositivo com um navegador da Web compatível com HTML 5.0. Combinações específicas de dispositivo/navegador que a Microsoft confirmou incluem:

- Microsoft Edge (última versão liberada publicamente) no Windows 10
- Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
- Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10
- Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Requisitos do software para Active Directory Federation Services 
Active Directory Federation Services (AD FS) no Windows Server 2016

O controlador de domínio deve ser Windows Server 2012 R2 ou posterior com um nível de domínio funcional de 2012 R2 ou superior

Para obter mais informações sobre níveis funcionais de domínio, consulte: 
- [O que são níveis funcionais do Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Noções básicas dos níveis funcionais dos Serviços de domínio Active Directory](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Requisitos de hardware e software para componentes do Retail
O Finance and Operations (local) não tem componentes de Retail no momento.

<a name="see-also"></a>Consulte também
--------

[Obtenha uma cópia de avaliação do Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

