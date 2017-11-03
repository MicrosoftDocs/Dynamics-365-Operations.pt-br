---
title: "Requisitos do sistema para implantações locais"
description: "Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, para as implantações locais."
author: kfend
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 25a6f326c57e84d6a7c356ac5407be7ed3095f83
ms.openlocfilehash: 5edc6f0b2240e9dd2d3b72a13f35e96f016aa013
ms.contentlocale: pt-br
ms.lasthandoff: 10/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Requisitos do sistema para implantações locais

[!include[banner](../includes/banner.md)]

Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, para as implantações locais. Antes de instalar o Finance and Operations, quando esta etapa for adequada, verifique se o sistema com o qual você está trabalhando atende ou excede os requisitos mínimos de rede, hardware e de software.

## <a name="network-requirements"></a>Requisitos de rede
O Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (local) pode funcionar em redes que usem IPv4 (protocolo IP versão 4) ou IPv6 (protocolo IP versão 6). Considere o ambiente de rede ao planejar seu sistema e use as seguintes diretrizes.

### <a name="network-response-time"></a>Tempo de resposta de rede
A seguinte tabela lista os requisitos mínimos de rede para a conexão entre o navegador da Web e o Servidor de Objetos de Aplicativo (AOS) e para a conexão entre AOS e o banco de dados em um sistema local.

| Alíquota     | Navegador da Web para AOS                      | AOS para banco de dados |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| Largura de banda | 50 quilobytes por segundo (KBps) por usuário | 100 megabytes por segundo (MBps) |
| Latência   | Menos de 250-300 milissegundos (ms)     | Menos de 1 ms (somente LAN [rede local]). O AOS e o banco de dados devem estar colocalizados. |

- O Finance and Operations (local) é projetado para redes que têm uma latência de 250–300 milissegundos (ms) ou menos. Esta latência é a latência de um cliente de navegador para o datacenter que hospeda o Finance and Operations.
- Os requisitos de largura de banda do Finance and Operations (local) dependem de seu cenário. Os cenários típicos exigem uma largura de banda de mais de 50 KBps entre o navegador e o servidor do Finance and Operations. No entanto, recomendamos mais largura de banda para cenários com requisitos de carga elevados, como cenários que envolvam espaços de trabalho ou personalização extensiva. O valor específico da largura de banda depende do uso.

Não há suporte para as implantações nas quais o AOS e o Banco de dados do Microsoft SQL Server estejam em datacenters diferentes. O AOS e o banco de dados do SQL Server devem estar colocalizados. 

Geralmente, o Finance and Operations é otimizado para reduzir viagens de ida e volta do navegador para o servidor. O número de viagens de ida e volta de um cliente do navegador para o datacenter é zero ou um para cada interação do usuário e a carga é compactada.

> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Recomendamos que você use uma simulação de um caso real em um ambiente de não produção do Finance and Operations como o melhor indicador de desempenho para seu caso específico. 

### <a name="lan-environments"></a>Ambientes de LAN
Em ambientes de LAN, a Área de Trabalho Remota da Microsoft no Microsoft Windows Server não é necessária para a conexão ao Finance and Operations. Entretanto, a Área de Trabalho Remota pode ser necessária para operações de manutenção nas VMs (máquinas virtuais) que compõem as implantações do servidor.

### <a name="wan-environments"></a>Ambientes de WAN
Em ambientes WAN (ampla área de rede), a Área de Trabalho Remota no Windows Server não é necessária para a conexão ao Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Requisitos de conectividade da Internet
O Finance and Operations (local) não exige conectividade com a Internet das estações de trabalho do usuário final. No entanto, alguns recursos não estarão disponíveis se não houver conectividade com a Internet.

|                    |   |
|--------------------|---|
| **Cliente de navegador** | Um cenário da intranet sem conectividade com a Internet é um ponto de design para a opção de implantação local. Alguns recursos que exigem serviço de nuvem não estarão disponíveis, como bibliotecas de Guias de tarefas e a Ajuda no LCS (Microsoft Dynamics Lifecycle Services ). |
| **Servidor**         | O AOS ou a camada do Microsoft Azure Service Fabric deve se comunicar com o LCS. O cliente baseado no navegador local não requer acesso à Internet. |
| **Telemetria**      | Os dados de telemetria poderão ser perdidos, se houver interrupções longas na conectividade. As interrupções na conectividade com o LCS não afetam a funcionalidade do aplicativo local. |
| **LCS**            | A conectividade ao LCS é necessária para implantação, implantação de código e operações de manutenção. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Transferência de dados de telemetria à nuvem
A maioria dos dados de telemetria é armazenada localmente e pode ser acessada usando o Visualizador de Eventos no Microsoft Windows. Um pequeno subconjunto de telemetria é transferido para o pipeline de telemetria do Microsoft na nuvem de diagnóstico. Os dados do cliente e os dados identificáveis do usuário não fazem parte dos dados de telemetria enviados à Microsoft. Os nomes da VM são enviados à Microsoft para ajudar com o gerenciamento e diagnóstico do ambiente do portal do LCS.

## <a name="domain-requirements"></a>Requisitos de domínio
Considere os seguintes requisitos de domínio ao instalar o Finance and Operations (local):

- As VMs que hospedam os componentes do Finance and Operations (local) devem pertencer a um domínio do Active Directory. Os serviços de domínio do Active Directory (AD DS) devem ser configurados no modo nativo.
- As VMs que executam componentes do Finance and Operations (local) devem ter acesso entre si. Esse acesso é configurado no AD DS. 
- O controlador de domínio deve ser o Microsoft Windows Server 2012 R2 ou posterior e o nível de domínio funcional deve ser 2012 R2 ou superior.

## <a name="hardware-requirements"></a>Requisitos de hardware
Esta seção descreve o hardware necessário para executar o Finance and Operations (local).

Os requisitos de hardware reais variam, com base na configuração do sistema, na composição de dados e nos aplicativos e recursos que você decide usar. Veja alguns dos fatores que podem afetar a escolha de hardware apropriado para o Finance and Operations (local):

- O número de transações por hora
- O número de usuários simultâneos

## <a name="minimum-infrastructure-requirements"></a>Requisitos mínimos de infraestrutura
O Finance and Operations (local) usa o Service Fabric para hospedar os serviços de AOS, Lote, Gerenciamento de dados, Management reporter e orquestrador no ambiente. 

O SQL Server deve ter uma configuração HADRON de alta disponibilidade definida que tenha pelo menos dois nós para uso em produção.

A ilustração a seguir mostra o número mínimo de nós que é recomendado para seu cluster do Service Fabric.

[![Número recomendado de nós para o cluster do Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Requisitos do Processador e de RAM
As tabelas a seguir listam o número de processadores e a quantidade de memória RAM necessária para cada função necessária para executar esta opção de implantação. Para saber mais, consulte os requisitos mínimos recomendados para um cluster autônomo do Service Fabric em [Planejar e preparar seu cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Se outro software da Microsoft for instalado no mesmo computador, o sistema também deve estar de acordo com os requisitos de hardware de tal software. Se outros aplicativos de servidor estiverem instalados no mesmo computador que o AOS, recomendamos limitar esses aplicativos de servidor a 1 gigabyte (GB) de RAM.

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

**Previsões mínimas de dimensionamento para implantações de produção e de área restrita\***

| Topologia                                        | Função                          | Número de instâncias |
|-------------------------------------------------|-------------------------------|---------------------|
| Produção                                      | AOS (Gerenciamento de dados, Lote)  | 3                   |
|                                                 | Management Reporter           | 2                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator\*\*              | 3                   |
| Área restrita                                         | AOS, Gerenciamento de dados, Lote   | 2                   |
|                                                 | Management Reporter           | 1                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator                  | 3                   |
| *Resumo das topologias de produção e de área restrita* |                               | *16*                |

\* Os números nesta tabela estão sendo validados por nossos clientes de visualização e podem ser ajustados com base nos comentários desses clientes.

\*\* O Orchestrator foi designado como o tipo de nó principal e também será usado para executar os serviços do Service Fabric.

**Estimativas iniciais para o SQL Server e o AD DS de back-end**

<table>
<thead>
<tr>
<th></th>
<th>Função</th>
<th>VMS/instâncias</th>
<th>Núcleos</th>
<th>Total de núcleos</th>
<th>Memória por instância (GB)</th>
<th>Memória total (GB)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Infraestrutura compartilhada</strong></td>
<td>SQL Server*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>Servidor de arquivos/Rede de área de armazenamento/Alto armazenamento disponível</td>
<td colspan="5"><p>O armazenamento back-end deve ser baseado em SSDs (unidades de estado sólido) em um tempo de execução da SAN (rede de área de armazenamento).</p>
<p>O tamanho e a produtividade de IOPS (operações de entrada/saída por segundo) são baseados no tamanho da carga de trabalho.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48</td>
</tr>
<tr>
<td><em>Resumo da infraestrutura compartilhada</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\* Os tamanhos do SQL Server são altamente dependentes das cargas de trabalho. Para saber mais, consulte [Dimensionamento de hardware para ambientes locais](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Armazenamento

- **AOS** – o Finance and Operations (local) usa um compartilhamento de protocolo SMB 3.0 para armazenar os dados não estruturados. Para obter mais informações, consulte [Espaços de Armazenamento Diretos no Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – as opções a seguir são viáveis:

    - Uma configuração de SSD altamente disponível
    - Uma SAN que é otimizada para a produtividade de OLTP (transação online)
    - DAS (armazenamento de conexão direta) de alto desempenho 

- **SQL Server e IOPS de gerenciamento de dados** – o armazenamento para o gerenciamento de dados e o SQL Server deve ter pelo menos 2.000 IOPS. IOPS de produção dependem de muitos fatores. Para saber mais, consulte [Dimensionamento de hardware para ambientes locais](hardware-sizing-on-premises-environments.md).
- **IOPS da VM** – cada VM deve ter pelo menos 100 IOPS de gravação.

## <a name="virtual-host-requirements"></a>Requisitos do host virtual
Ao configurar os hosts virtuais para um ambiente do Finance and Operations (local), consulte as diretrizes em [Planejar e preparar seu cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) e [Descrevendo um cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Host cada virtual deve ter núcleos suficientes para a infraestrutura que está sendo dimensionada. Várias configurações avançadas são possíveis, onde o SQL Server reside no hardware físico, mas todo o resto é virtualizado. Se o SQL Server for virtualizado, o subsistema de disco deve ser uma SAN rápida ou equivalente. Em todos os casos, certifique-se de que a configuração básica do host virtual é altamente disponível e redundante. Em todos os casos, quando a virtualização for usada, nenhum instantâneo de VM deve ser obtido.

## <a name="software-requirements-for-all-server-computers"></a>Requisitos de software todos os computadores do servidor
O seguinte software deve estar presente em um computador antes de quaisquer componentes do Finance and Operations (local) serem instalados:

- A versão 4.5.1 ou posterior do Microsoft .NET Framework
- Service Fabric

Para saber mais, consulte [Planejar e preparar seu cluster do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Sistemas operacionais do servidor suportados
A tabela a seguir lista os sistemas operacionais do servidor que são suportados para os componentes do Finance and Operations.

| Sistema operacional                                     | Observação |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Datacenter ou Padrão | Esses requisitos são para o banco de dados e o cluster do Service Fabric que hospeda o AOS. |

## <a name="software-requirements-for-database-servers"></a>Requisitos de software para servidores do banco de dados

- Somente as versões de 64 bits do SQL Server 2016 são suportadas.
- Em um ambiente de produção, recomendamos a instalação da última atualização cumulativa(CU) da versão do SQL Server que você está usando.
- O Finance and Operations (local) suporta agrupamentos que não diferenciam maiúsculas de minúsculas, diferenciam acentos, diferenciam kana, não diferenciam largura. O agrupamento deve corresponder à localidade dos computadores Windows que estão executando instâncias do AOS. Se estiver configurando uma nova instalação, recomendamos que você selecione um agrupamento do Windows, em vez de um agrupamento do SQL Server. Para obter mais informações sobre como selecionar um agrupamento para um banco de dados do SQL Server, consulte [documentação do SQL Server](/sql/sql-server/sql-server-technical-documentation).

A tabela a seguir lista as versões do SQL Server que são suportadas para os bancos de dados do Finance and Operations. Para obter mais informações, consulte os requisitos mínimos de hardware para [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Necessidade                                                      | Observação |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition ou Enterprise Edition | Para os requisitos de hardware do SQL Server 2016, consulte [Requisitos de hardware e o software para instalar SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-application-object-server-aos"></a>Os requisitos do software para AOS (Servidor de Objetos de Aplicativo) 
- SQL Server Integation Services (SSIS)

## <a name="software-requirements-for-reporting-server-bi"></a>Requisitos do software para Servidor de Relatório (BI)
- SQL Server Reporting Services (SSRS)

## <a name="software-requirements-for-client-computers"></a>Requisitos de software todos os computadores do cliente
O aplicativo da Web do Finance and Operations pode ser executado em qualquer dispositivo que tenha um navegador da Web compatível com HTML 5.0. Veja algumas das combinações específicas de dispositivo/navegador que a Microsoft confirmou:

- Microsoft Edge (última versão liberada publicamente) no Windows 10
- Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
- Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10
- Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Requisitos do software para Active Directory Federation Services 
Active Directory Federation Services (AD FS) no Windows Server 2016 é necessário.

O controlador de domínio deve ser o Windows Server 2012 R2 ou posterior e o nível de domínio funcional deve ser 2012 R2 ou superior. Para saber mais sobre níveis funcionais de domínio, consulte as páginas a seguir:

- [O que são níveis funcionais do Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Noções básicas dos níveis funcionais dos Serviços de domínio Active Directory](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office suportados
Os seguintes aplicativos do Microsoft Office têm suporte nas implantações de nuvem e locais do Finance and Operations:

-   Para executar os suplementos do Microsoft Excel e Microsoft Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para saber mais sobre os requisitos de versão, consulte [Solução de problemas de integração do Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Para exibir documentos que são gerados pela exportação para Excel ou exportar para funcionalidade do Word, você deve ter o Microsoft Office 2007 ou posterior instalado.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Requisitos de hardware e software para componentes do Retail
No momento, o Finance and Operations (local) não inclui componentes do Retail.

