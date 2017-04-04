---
title: Requisitos do sistema
description: "Este tópico lista os requisitos de sistema para a versão atual do Microsoft Dynamics 365 para as operações."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Requisitos do sistema

Este tópico lista os requisitos de sistema para a versão atual do Microsoft Dynamics 365 para as operações.

<a name="supported-web-browsers"></a>Navegadores da web suportados
----------------------

Microsoft Dynamics 365 para a aplicação da web de operações pode executar em qualquer dos seguintes browsers da Web que executam os sistemas operacionais especificado:

-   Faixas da Microsoft (publicamente disponível - a versão a última Windows 10)
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (publicamente - a versão disponível o último) em tablet de O Windows 10, de O Windows 8.1, do Windows 8, do Windows 7, ou de Nexus Google 10
-   Apple Safari (publicamente - a versão disponível o último) em Mac OS X 10.10 (Yosemite), EL (10.11) Capitan ou 10.12 (serra), ou iPad Apple

Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software. **Observações:**

-   Capturar imagens geradas gravador de tarefas e as incluir em documentos do Microsoft Word, você deve ter uma extensão de Chrome instalada. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   Editor do fluxo de trabalho é iniciado como um aplicativo ClickOnce. Apenas as faixas e Internet Explorer Microsoft (suportado em uma versão do Microsoft Windows) suportam aplicativos ClickOnces. O aplicativo ClickOnce do editor de fluxo de trabalho a um sistema operacional compatível de 64 bits.
-   O Designer do relatório financeiro é iniciado como um aplicativo ClickOnce. Requer um sistema operacional compatível de 64 bits. Se estiver usando Chrome, instale-o uma extensão de ClickOnce para baixar o cliente do designer de relatórios. Se estiver usando Chrome com em incógnito o modo, verifique se a extensão de ClickOnce está habilitada em incógnito também para o forma.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navegadores da web suportados para o Retail Cloud POS

O Retail POS do nuvem para dynamics 365 para operações pode executar em qualquer dos seguintes browsers da Web que executam os sistemas operacionais especificado:

-   Faixas da Microsoft (publicamente disponível - a versão a última Windows 10)
-   Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7
-   Chrome (publicamente - a versão disponível o último) Windows 10, Windows 8.1, ou Windows 7

## <a name="network-requirements"></a>Requisitos líquidos
-   O dynamics 365 é criada para operações com redes latência de menos de 150 de milissegundos (ms). Esta é a latência em um cliente do navegador ao centro de dados de Microsoft Azure que hospeda o dynamics 365 para as operações. Recomendamos que você teste de rede< a latência em http://www.azurespeed.com>.
-   Os requisitos de largura de banda para dynamics 365 para operações dependem do cenário. A maioria de cenários típicos exigem uma largura de banda de mais de 50 por quilobytes de segundo Kbps (). Entretanto, para os cenários que têm requisitos alto de carga, como espaços de trabalho ou os cenários envolvendo a personalização extensiva mais, largura de banda a recomendada.

Geralmente, o dynamics 365 para operações é otimizada para A Internet. O número de viagens de ida e volta de um cliente do navegador ao centro de dados de Azure é muito pequeno, a carga inteira foi compactada. ** Aviso: ** Não calcular requisitos largura de banda de um local do cliente ao multiplicar o número de usuários pelos requisitos mínimos largura de banda. Uso simultâneas de uma localização específica será muito difícil de cálculo. Para clientes que são referidos sobre requisitos de largura de banda, use uma versão de visualização do 365 para as operações.

## <a name="net-framework-requirements"></a>requisitos do .NET Framework
O dynamics 365 para operações da versão 4.6.2 do .NET Framework para todos clique- depois de aplicativos, como o agente de roteamento de documento. Para obter instruções de instalação, consulte [instalando .NET Framework] (https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Aplicativos suporte do Microsoft Office
-   Para executar o Microsoft Excel e o exprimir suplementos, você deve ter o Microsoft Office de 2016 ou Windows Mac instalado. Para obter mais detalhes sobre requisitos de liberação, consulte [] solução de problemas de integração de O Office (/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para exibir os documentos que são geradas por exportar excel ou exportar para exprimir a funcionalidade, você deve ter o Microsoft Office de 2007 ou mais recente instalado.

## <a name="retail-modern-pos-requirements"></a>Requisitos modernos o retail POS
### <a name="supported-operating-systems"></a>Sistemas operacionais suporte

-   O Retail moderno de varejo é um aplicativo de 32 bits, mas será executada em arquiteturas x86 ou x64.
-   O Retail moderno de varejo tem suporte apenas em O Windows 10 conservação edições de longo prazo da empresa, de, e a empresa da filial (LTSB).

### <a name="minimum-system-requirements"></a>Requisitos de sistema mínimos

-   A solução suportado mínima é 1280 × 1024.
-   O computador que vende ao retail headquarters moderno executa sobre deve atender a esses requisitos:
    -   Necessário, pelo menos, um processador de duplo- core executado em nenhum menos de 2 ghz (GHz).
    -   Necessário, pelo menos, 3 de gigabytes (GB) de RAM.
    -   Deve ter acesso à internet.

## <a name="retail-hardware-station-requirements"></a>Requisitos de varejo da estação de hardware
### <a name="supported-operating-systems"></a>Sistemas operacionais suporte

-   A estação de varejo de hardware é um aplicativo de 32 bits, mas será executada em arquiteturas x86 ou x64.
-   A estação de varejo de hardware é suportada nos sistemas operacionais:
    -   Windows 7 Professional, empresa, além edições finais ** observação: ** O Windows 7 tem suporte apenas se Internet Explorer 11 está instalado manualmente no sistema.
    -   Profissional de atualizações 1 de O Windows 8.1, a empresa, além edições inseridos
    -   Windows 10 edições fiscal, a empresa, e a empresa LTSB

### <a name="minimum-system-requirements"></a>Requisitos de sistema mínimos

O computador deve atender a todas requisitos de sistema para instalar e usar os seguintes itens:

-   Serviços de Informações da Internet (IIS)
-   Hardware de terceiros

## <a name="retail-store-scale-unit-requirements"></a>Requisitos de unidade de escala de fábrica
### <a name="supported-operating-systems"></a>Sistemas operacionais suporte

-   A unidade de escala de fábrica é um aplicativo de 32 bits, mas será executada em arquiteturas x86 ou x64.
-   A unidade de escala de fábrica é suportada nos sistemas operacionais:
    -   Windows 7 Professional, empresa, além edições finais
    -   Profissional de atualizações 1 de O Windows 8.1, a empresa, além edições inseridos
    -   Windows 10 edições fiscal, a empresa, e a empresa LTSB

### <a name="minimum-system-requirements"></a>Requisitos de sistema mínimos

-   4 GB de RAM
-   1.6 De pico ghz de velocidade do CPU por principal (dois núcleos é o mínimo.)
-   Pelo menos 10 GB de espaço livre (o base de dados de canal pode exigir uma grande quantidade de espaço.)

### <a name="recommended-system-requirements"></a>Requisitos de sistema recomendadas

-   6 GB de RAM
-   2.4 De i7 (ou de equivalente) pico ghz de velocidade do CPU por principal (quatro núcleos é recomendado.)
-   Pelo menos 10 GB de espaço livre (o base de dados de canal pode exigir uma grande quantidade de espaço.)

## <a name="requirements-for-development-on-local-vms"></a>Requisitos do desenvolvimento em VMs local
Para obter informações sobre os requisitos do desenvolvimento em máquinas virtuais (VMs) locais, consulte em [locais] em execução de #vm-that-is-running-in-premises VM (/dynamics365/operations/dev-itpro/dev-tools/access-instances).

<a name="see-also"></a>Consulte também
--------

[Obter uma cópia de avaliação do 365 para operações] (/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


