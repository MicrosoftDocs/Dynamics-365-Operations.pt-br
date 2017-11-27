---
title: "Requisitos de sistema para implantações na nuvem"
description: "Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, para as implantações na nuvem."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a>Requisitos de sistema para implantações na nuvem

[!include[banner](../includes/banner.md)]

Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, para as implantações na nuvem. Antes de instalar o Finance and Operations, quando esta etapa for adequada, verifique se o sistema com o qual você está trabalhando atende ou excede os requisitos mínimos de rede, hardware e de software.

## <a name="supported-web-browsers"></a>Navegadores da web suportados
O aplicativo de web pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10
-   Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad

Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software. 

> [!NOTE]
> -   Você deve instalar uma extensão do Chrome de pré-lançamento para habilitar o Gravador de tarefas a fazer capturas de tela e incluí-las em documentos do Microsoft Word que são gerados. <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce. Somente o Microsoft Edge e o Internet Explorer (em uma versão com suporte do Microsoft Windows) suportam aplicativos ClickOnce. O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.
> -   O Report Designer for Financial Reporting é iniciado como um aplicativo ClickOnce. Ele requer um sistema operacional compatível com 64 bits. Se estiver usando o Chrome, instale uma extensão ClickOnce para baixar o cliente de Designer de Relatórios. Se usar o Chrome no modo de navegação anônima, verifique se a extensão ClickOnce também está ativada para o modo de navegação anônima.
> -   Para visualizar os arquivos PDF, recomendamos que você use navegadores como o Microsoft Edge (última versão liberada publicamente) no Windows 10 ou o Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navegadores da web suportados para o Retail Cloud POS

O PDV de nuvem de varejo pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, ou Windows 7

## <a name="network-requirements"></a>Requisitos de rede
-   O Finance and Operations foi projetado para redes que têm uma latência de 250–300 milissegundos (ms) ou menos. Esta latência é a latência de um cliente de navegador para o datacenter do Microsoft Azure que hospeda o Finance and Operations. Recomendamos que teste a latência da rede em <http://www.azurespeed.com>.
-   Os requisitos de largura do Finance and Operations dependem de seu cenário. A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps). No entanto, recomendamos mais largura de banda para cenários com requisitos de carga elevados, como cenários que envolvam espaços de trabalho ou personalização extensiva.

Em geral, o Finance and Operations é otimizado para a Internet. O número de viagens de ida e volta de um cliente de navegador para o datacenter do Azure é muito pequeno e toda a carga útil é compactada. 

> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Os clientes que estão preocupados com os requisitos de largura de banda devem usar uma versão de visualização do Finance and Operations.

## <a name="net-framework-requirements"></a>Requisitos do .NET Framework
O Finance and Operations requer a versão 4.6.2 do Microsoft .NET Framework para todos os aplicativos ClickOnce, como o agente de roteamento de documentos. Para obter instruções de instalação, consulte [Instalando o .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office suportados
Os seguintes aplicativos do Microsoft Office têm suporte nas implantações de nuvem e locais do Finance and Operations:

-   Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para saber mais sobre os requisitos de versão, consulte [Solução de problemas de integração do Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Para exibir documentos que são gerados pela exportação para Excel ou exportar para funcionalidade do Word, você deve ter o Microsoft Office 2007 ou posterior instalado.

## <a name="retail-modern-pos-requirements"></a>Requisitos modernos de POS de varejo

> [!NOTE]
> Se o Retail Modern POS usar um banco de dados offline, o computador deverá atender a todos os requisitos do sistema para o Microsoft SQL Server. Um banco de dados offline do Retail Modern POS funcionará no Microsoft SQL Server 2012 com o Service Pack 3 ou posterior, o Microsoft SQL Server 2014 com Service Pack 2 ou posterior, e o Microsoft SQL Server 2016. Recomendamos usar sempre a versão mais recente disponível e a instalação todos os service packs mais recentes.

### <a name="supported-operating-systems"></a>Sistemas operacionais suportados

-   O Retail POS moderno é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.
-   O varejo POS moderno é suportado somente em edições de ramal de serviço de longo prazo Enterprise (LTSB), do Windows 10 Pro, e Enterprise.

### <a name="minimum-system-requirements"></a>Requisitos mínimos do sistema

-   A resolução mínima suportada é 1280 × 1024.
-   O computador em que o Retail Modern POS funciona deve atender a esses requisitos:

    -   Ele deve ter, no mínimo, um processador dual-core que funciona a não menos de 2 gigahertz (GHz).
    -   Ele deve ter, no mínimo, 3 gigabytes (GB) de RAM.
    -   Ele deve ter acesso à Internet.

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

-   O conector do Microsoft Dynamics AX tem dois instaladores separados, um para o Serviço de Conector do Async Server e um para o Serviço em tempo Real do Dynamics AX 2012 R3.
-   Ambos os componentes são aplicativos de 32 bits, mas serão executados em arquiteturas x86 e x64.
-   Os componentes são suportados nos seguintes sistemas operacionais:

    -   Edições do Windows 7 Professional, Enterprise, e Ultimate
    -   Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas
    -   Edições LTSB Enterprise, Windows 10 Pro, e Enterprise
    -   Microsoft Windows Server 2012 R2 e Microsoft Windows Server 2016

### <a name="minimum-system-requirements"></a>Requisitos mínimos do sistema
-   2 GB de RAM, (4 GB de RAM são recomendados.)
-   Velocidade máxima de CPU de 1,6 GHz por núcleo (dois núcleos no mínimo.)
-   Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)

## <a name="requirements-for-development-on-local-vms"></a>Requisitos do desenvolvimento em VMs locais
Para obter informações sobre os requisitos de desenvolvimento em máquinas virtuais locais (VMs), consulte [VM em execução no local](../../dev-itpro/dev-tools/access-instances.md).


## <a name="see-also"></a>Consulte também

[Obtenha uma cópia de avaliação do Dynamics 365 for Finance and Operations, edição Enterprise](../../dev-itpro/dev-tools/get-evaluation-copy.md)

