---
title: Visão geral de impressão do documento
description: Você pode imprimir documentos usando uma impressora local ou um dispositivo conectado em rede. Este artigo fornece uma visão geral de como os documentos são impressos.
author: TJVass
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1d64a2efeade5e9ba24f4dfe61c861f5a4cbad4
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680087"
---
# <a name="document-printing-overview"></a>Visão geral de impressão do documento

[!include [banner](../includes/banner.md)]

Você pode imprimir documentos usando uma impressora local ou um dispositivo conectado em rede. Este artigo fornece uma visão geral de como os documentos são impressos.

## <a name="printing-overview"></a>Visão geral de impressão

O aplicativo fornece serviços integrados e aplicativos cliente que facilitam a geração, o armazenamento e a distribuição de documentos que ofereçam suporte à atividade comercial. Você pode imprimir documentos usando uma impressora local ou um dispositivo conectado em rede. Além disso, você pode exportar páginas e relatórios diretamente do cliente, como arquivos PDF ou documentos do Microsoft Office. Por fim, a carga de trabalho distribuída permite que você imprima documentos comerciais diretamente de um dispositivo móvel, usando recursos de rede. Embora os requisitos de impressão variem, todas as indústrias devem criar cópias impressas de documentos comerciais usando o aplicativo. A impressão de documentos nos dispositivos de rede dos aplicativos hospedados apresenta um conjunto de desafios exclusivo. Eis alguns exemplos:

- Os drivers de impressão talvez não esteja disponíveis do dispositivo do usuário.
- O dispositivo do usuário talvez não esteja conectado à rede corporativa.

Usando um host dedicado e seguindo algumas etapas fáceis, os administradores do sistema podem configurar implantações, de forma que os usuários possam imprimir diretamente dos aplicativos comerciais em dispositivos de rede.

### <a name="application-printing-scenarios"></a>Cenários impressão de aplicativo 

A tabela a seguir descreve os três cenários principais de impressão.

| Cenário                        | Meta                                                      | Solução |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. Imprimindo o que você vê        | Imprime o que é mostrado atualmente no navegador.             | Uma versão de "impressão amigável" da página da Web é gerada para o navegador. |
| 2. Impressão interativa         | Imprime um documento de precisão em um dispositivo conectado localmente. | Você pode exportar uma versão PDF do relatório e baixá-la no navegador. |
| 3. Impressão em um dispositivo da rede | Enviar um documento de precisão para um dispositivo da impressora de domínio.     | Um documento de precisão é enviado a um aplicativo cliente que é executado em um servidor que está hospedado no domínio do cliente. |

Como a solução varia, dependendo do cenário, os aplicativos fornecem serviços e ferramentas internas para ajudar os usuários a atingirem suas metas:

- **Cenário 1** é suportado pela renderização do navegador do cliente HTML5.
- **Cenário 2** usa aplicativos cliente e serviços do Microsoft 365.
- **Cenário 3** requer suporte de aplicativos cliente e de serviços que são hospedados no Microsoft Azure.

Além da plataforma que é implantada na assinatura do Azure, os aplicativos Finance and Operations fornecem aos clientes um aplicativo integrado, do primeiro participante do Azure que os ajudam a usar de forma mais fácil os dispositivos hospedados de domínio para imprimir documentos.

## <a name="service-overview"></a>Visão geral do serviço
Enquanto os documentos que são produzidos pelos aplicativos hospedados estão aguardando para serem impressos em um dispositivo conectado por rede, eles são armazenados no armazenamento de blob do Azure. [Instalar o Agente de Roteamento de Documentos para habilitar a impressão de rede](install-document-routing-agent.md) usa a autenticação do Azure para estabelecer um canal seguro para os serviços do Azure.

**Sequência de execução**

1. O relatório é gerado pelo Microsoft SQL Server Reporting Services (SSRS) e armazenado no armazenamento do blob do Azure. As configurações de impressora anexada são armazenadas com o documento.
2. O Agente de Roteamento de Documento consulta a fila do Azure Service Bus para trabalhos ativos.
3. O documento é baixado pelo Agente de Roteamento de Documentos e colocado em spool na impressora de rede.

A solução baseada no cliente permite que os clientes gerenciem a escala de suas necessidades de impressão. Os clientes com cargas de trabalho de impressão de grande volume podem instalar muitos Agentes de Roteamento de Documentos para aumentar o número de operações de impressão simultâneas. Como alternativa, alguns clientes exigem algumas instalações do Agente de Roteamento de Documentos para tratar suas necessidades de impressão antecipadas.

### <a name="service-components-for-network-printing"></a>Componentes do serviço para impressão de rede

O diagrama a seguir exibe os componentes básicos que ajudam a suportar operações de impressão de rede.

[![componentes de serviço para impressão de rede\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

Observe que uma única impressora pode ser registrada em vários Agentes de Roteamento de Documentos. Para resolver as preferências de impressora, o serviço hospedado usa o caminho de rede que identifica exclusivamente cada impressora de rede. Como consequência, mesmo quando uma impressora é registrada por vários clientes, ela é exibida como uma seleção única na lista de impressoras disponíveis nos aplicativos.
