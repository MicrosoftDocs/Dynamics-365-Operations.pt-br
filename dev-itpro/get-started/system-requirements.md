---
title: Requisitos do sistema
description: "Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 724ee7ec29f8a9c4e8cc0b244193cd6c83c37f03
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="system-requirements"></a>Requisitos do sistema

[!include[banner](../includes/banner.md)]


Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

<a name="supported-web-browsers"></a>Navegadores da web suportados
----------------------

O aplicativo de web pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10
-   Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad

Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software. 

**Observações:**

-   Uma extensão do Chrome de pré-lançamento deve ser instalada para permitir que as capturas de tela sejam capturadas pelo Task Recorder e incluídas em documentos do Microsoft Word gerados. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
-   O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce. Somente o Microsoft Edge e o Internet Explorer (em uma versão com suporte do Microsoft Windows) suportam aplicativos ClickOnce. O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.
-   O Report Designer for Financial Reporting é iniciado como um aplicativo ClickOnce. Ele requer um sistema operacional compatível com 64 bits. Se estiver usando o Chrome, instale uma extensão ClickOnce para baixar o cliente de designer de relatórios. Se estiver usando o Chrome com o modo de navegação anônima, verifique se a extensão ClickOnce também está ativada para o modo de navegação anônima.
-   Para visualizar os arquivos PDF, recomendamos que você use navegadores como Microsoft Edge (última versão liberada publicamente) no Windows 10 ou Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou tablet Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navegadores da web suportados para o Retail Cloud POS

O PDV de nuvem de varejo pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, ou Windows 7

## <a name="network-requirements"></a>Requisitos de rede
-   O Dynamics 365 for Finance and Operations, Enterprise Edition, foi projetado para redes com latência entre 250 e 300 milissegundos (ms) ou menos. Esta é a latência de um cliente de navegador para o centro de dados Microsoft Azure que hospeda Dynamics 365 for Finance and Operations. Recomendamos que teste a latência da rede em <http://www.azurespeed.com>.
-   Os requisitos de largura de banda dependem do seu cenário. A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps). No entanto, para cenários com requisitos de carga útil elevados, como espaços de trabalho ou cenários que envolvem personalização extensiva, recomenda-se mais largura de banda.

Em geral, o Finanças e Operações é otimizado para a Internet. O número de viagens de ida e volta de um cliente de navegador para o centro de dados do Azure é pequeno e toda a carga útil é compactada. 

**Aviso:** Não compute os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é difícil de calcular. Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de visualização do Finanças e Operações.

## <a name="net-framework-requirements"></a>Requisitos do .NET Framework
O .NET Framework versão 4.6.2 é necessário para todos os aplicativos ClickOnce, como o agente de roteamento de documentos. Para obter instruções de instalação, consulte [Instalando o .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office suportados
-   Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para obter mais detalhes sobre os requisitos de versão, consulte [Solução de problemas de integração Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para exibir documentos que são gerados pela exportação para Excel ou exportar para funcionalidade do Word, você deve ter o Microsoft Office 2007 ou posterior instalado.

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
    -   Windows 7 Professional, Enterprise, e Ultimate **Observação:** o Windows 7 é suportado apenas se o Internet Explorer 11 for instalado manualmente no sistema.
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

<a name="see-also"></a>Consulte também
--------

[Obtenha uma cópia de avaliação do Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)





