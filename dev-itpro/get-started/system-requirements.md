---
title: Requisitos do sistema
description: "Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Operations."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 86053196a3aad6b7b5d7830860e1af347dd969d8
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="system-requirements"></a>Requisitos do sistema

[!include[banner](../includes/banner.md)]


Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Operations.

<a name="supported-web-browsers"></a>Navegadores da web suportados
----------------------

O aplicativo de web do Microsoft Dynamics 365 for Operations pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10
-   Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad

Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software. **Observações:**

-   Para capturar imagens geradas a partir do Gravador de Tarefas e incluí-las em documentos do Microsoft Word, você deve ter uma extensão do Chrome instalada. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce. Somente o Microsoft Edge e o Internet Explorer (em uma versão com suporte do Microsoft Windows) suportam aplicativos ClickOnce. O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.
-   O Report Designer for Financial Reporting é iniciado como um aplicativo ClickOnce. Ele requer um sistema operacional compatível com 64 bits. Se estiver usando o Chrome, instale uma extensão de ClickOnce para baixar o cliente de designer de relatórios. Se estiver usando o Chrome com o modo de navegação anônima, verifique se a extensão ClickOnce também está ativada para o modo de navegação anônima.
-   Para visualizar os arquivos PDF, recomendamos que você use navegadores modernos como Microsoft Edge (última versão liberada publicamente) no Windows 10 ou Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou tablet Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navegadores da web suportados para o Retail Cloud POS

O Retail Cloud POS do Dynamics 365 for Operations pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:

-   Microsoft Edge (última versão liberada publicamente) no Windows 10
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, ou Windows 7

## <a name="network-requirements"></a>Requisitos de rede
-   O Dynamics 365 for Operations foi projetado para redes com latência inferior a 150 milissegundos (ms). Esta é a latência de um cliente de navegador para o centro de dados Microsoft Azure que hospeda Dynamics 365 para operações. Recomendamos que teste a latência da rede em <http://www.azurespeed.com>.
-   Os requisitos de largura de banda para o Dynamics 365 for Operations dependem do seu cenário. A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps). No entanto, para cenários com requisitos de carga útil elevados, como espaços de trabalho ou cenários que envolvem personalização extensiva, recomenda-se mais largura de banda.

Em geral, o Dynamics 365 for Operations é otimizado para a Internet. O número de viagens de ida e volta de um cliente de navegador para o centro de dados do Azure é muito pequeno e toda a carga útil é compactada. **Aviso:** Não compute os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de visualização do Dynamics 365 for Operations.

## <a name="net-framework-requirements"></a>Requisitos do .NET Framework
O Dynamics 365 for Operations requer o .NET Framework versão 4.6.2 para todos os aplicativos de clique único, como o agente de roteamento de documentos. Para obter instruções de instalação, consulte [Instalando o .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office suportados
-   Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para obter mais detalhes sobre os requisitos de versão, consulte [Solução de problemas de integração Office](/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
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

## <a name="requirements-for-development-on-local-vms"></a>Requisitos do desenvolvimento em VMs locais
Para obter informações sobre os requisitos de desenvolvimento em máquinas virtuais locais (VMs), consulte [VM em execução no local](../dev-tools/access-instances.md).

<a name="see-also"></a>Consulte também
--------

[Obter uma cópia de avaliação do Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)




