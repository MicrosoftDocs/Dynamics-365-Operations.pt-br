---
title: Tipo de destino de ER da impressora
description: Este tópico explica como configurar um destino de impressora para cada componente de PASTA ou ARQUIVO de um formato de relatório eletrônico (ER).
author: NickSelin
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 7749a458020de664d00e81ccf0e480ae459da617
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893995"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destino da impressora

[!include [banner](../includes/banner.md)]

Você pode enviar um documento gerado diretamente para uma impressora da rede para impressão direta.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, você deve instalar e configurar o Agente de Roteamento de Documentos e registrar as impressoras da rede. Para obter mais informações, consulte [Instalar o Agente de Roteamento de Documentos para habilitar a impressão de rede](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>Disponibilizar o destino da impressora

Para disponibilizar o destino da **Impressora** na instância atual do Microsoft Dynamics 365 Finance, vá para o espaço de trabalho **Gerenciamento de recursos** e ative os seguintes recursos, nesta ordem:

1. Converta os documentos de saída do Relatório Eletrônico de formatos do Microsoft Office em PDF.
2. Agente de Roteamento de Documentos como destino do Relatório Eletrônico para documentos de saída

[![Ativando o recurso de destino da impressora do ER no Gerenciamento de recursos](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Aplicabilidade

O destino da **Impressora** pode ser configurado somente para componentes de arquivo usados para gerar saída no formato PDF imprimível (elementos de formato de arquivo PDF ou Fusão de PDFs) ou Microsoft Office Excel/Word (arquivo do Excel). Quando a saída é gerada no formato PDF, ela é enviada para uma impressora. Quando a saída é gerada no formato do Microsoft Office, ela é automaticamente convertida no formato PDF e enviada a uma impressora.

### <a name="limitations"></a>Limitações

O destino da **Impressora** é implementado somente para implantações em nuvem.

### <a name="use-the-printer-destination"></a>Usar o destino da Impressora

1. Defina a opção **Habilitado** como **Sim** para enviar um documento gerado para uma impressora.
2. No campo **Nome da impressora**, selecione a impressora de rede necessária.
3. Defina a opção **Salvar em arquivo de impressão?** como **Sim** para armazenar a saída gerada no arquivo de impressão, de modo que ela esteja disponível para impressão futura. Para acessar posteriormente a saída arquivada, vá para **Administração da organização** \> **Consultas e relatórios** \> **Arquivo de relatório**.

[![Usando o destino da Impressora](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> A opção **Converter em PDF** não precisa ser ativada quando você configura o destino da **Impressora**. A conversão em PDF para fins de impressão ocorrerá mesmo que a opção seja desativada.

Para usar uma [orientação de página](electronic-reporting-destinations.md#SelectPdfPageOrientation) específica ao imprimir um documento de saída no formato Excel, você deve ativar a opção **Converter para PDF**. Quando você definir a opção **Converter para PDF** como **Sim**, o campo **Orientação da página** ficará disponível. No campo **Orientação da página**, você pode selecionar uma orientação de página.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]