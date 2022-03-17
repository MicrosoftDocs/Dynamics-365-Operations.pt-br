---
title: Tipo de destino de ER da impressora
description: Este tópico explica como configurar um destino de impressora para cada componente de PASTA ou ARQUIVO de um formato de relatório eletrônico (ER).
author: NickSelin
ms.date: 02/14/2022
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
ms.openlocfilehash: 2513fc4f86519c71602089cd46e9757813b1a708
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388279"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destino da impressora

[!include [banner](../includes/banner.md)]

Você pode enviar um documento gerado diretamente para uma impressora da rede para impressão direta.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, você deve instalar e configurar o Agente de Roteamento de Documentos e registrar as impressoras da rede. Para obter mais informações, consulte [Instalar o Agente de Roteamento de Documentos para habilitar a impressão de rede](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>Disponibilizar o destino da impressora

Para disponibilizar o destino da **Impressora** na instância atual do Microsoft Dynamics 365 Finance, Acesse o espaço de trabalho **Gerenciamento de recursos** e ative os seguintes recursos, nesta ordem:

1. Converta os documentos de saída do Relatório Eletrônico de formatos do Microsoft Office em PDF.
2. Agente de Roteamento de Documentos como destino do Relatório Eletrônico para documentos de saída

[![Ativando o recurso de destino da impressora do ER no Gerenciamento de recursos.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Aplicabilidade

#### <a name="pdf-printing"></a>Impressão de PDF

Em versões do Finance antes da 10.0.18, o destino da **Impressora** pode ser configurado somente para componentes de arquivo usados para gerar saída no formato PDF imprimível (elementos de formato **Fusão de PDFs** ou **arquivo PDF**) ou Microsoft Office Excel e Word (elemento de formato **arquivo do Excel**). Quando a saída é gerada no formato PDF, ela é enviada para uma impressora. Quando a saída é gerada no formato do Office, usando o elemento de formato **arquivo do Excel**, ela é automaticamente convertida no formato PDF e enviada a uma impressora.

No entanto, a partir da versão 10.0.18, você pode configurar o destino da **Impressora** para o elemento de formato de **Arquivo comum**. Esse elemento de formato é usado principalmente para gerar saída no formato TXT ou XML. Você pode configurar um formato ER contendo o elemento formato de **Arquivo comum** como o elemento de formato raiz e o elemento formato de **Conteúdo binário** como o único elemento aninhado abaixo dele. Nesse caso, o elemento de formato de **Arquivo comum** produzirá saída no formato especificado pela associação configurada para o elemento de formato de **Conteúdo binário**. Por exemplo, você pode configurar essa associação para [preencher](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) este elemento com o conteúdo de um anexo [Gerenciamento de documentos](../../fin-ops/organization-administration/configure-document-management.md) no formato PDF ou Office (Excel ou Word). Você pode imprimir a saída usando o destino de **Impressora** configurado. 

> [!NOTE]
> Quando você seleciona o elemento de formato **Comum\\Arquivo** para configurar o destino da **Impressora**, não há como garantir, em tempo de design, que o elemento selecionado produzirá saída no formato PDF ou saída que possa ser convertido em formato PDF. A seguinte mensagem de aviso é exibida: "Verifique se a saída gerada pelo componente de formato selecionado pode ser convertida em PDF. Caso contrário, desmarque a opção 'Converter em PDF'." Você deve executar etapas para ajudar a evitar problemas de tempo de execução quando saídas não-PDF ou não conversíveis em PDF são fornecidas para impressão no tempo de execução. Se você espera receber a saída no formato Office (Excel ou Word), a opção **Converter em PDF** deve ser selecionada.
>
> Na versão 10.0.26 e posterior, para usar a opção **Converter em PDF**, selecione **PDF** para o parâmetro **Tipo de roteamento de documentos** do destino de **Impressora** configurado.

#### <a name="zpl-printing"></a>Impressão de ZPL

Na versão 10.0.26 e posterior, você pode configurar o destino de **Impressora** para o elemento de formato **Comum\\Arquivo**, selecionando **ZPL** para o parâmetro **Tipo de roteamento de documentos**. Nesse caso, a opção **Converter em PDF** será ignorada no tempo de execução e a saída TXT ou XML será enviada diretamente para uma impressora selecionada usando o contrato ZPL (Linguagem de Programação Zebra) do [Agente de Roteamento de Documentos (DRA)](install-document-routing-agent.md). Use este recurso para um formato ER que representa um layout de etiqueta de ZPL II para imprimir várias etiquetas.

[![Definir o parâmetro Tipo de roteamento de documentos na caixa de diálogo Configurações de destino.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Para obter mais informações sobre esse recurso, consulte [Criar uma nova solução ER para imprimir etiquetas ZPL](er-design-zpl-labels.md).

### <a name="limitations"></a>Limitações

O destino da **Impressora** é implementado somente para implantações em nuvem.

### <a name="use-the-printer-destination"></a>Usar o destino da Impressora

1. Defina a opção **Habilitado** como **Sim** para enviar um documento gerado para uma impressora.
2. No campo **Nome da impressora**, selecione a impressora de rede necessária.
3. Defina a opção **Salvar em arquivo de impressão?** como **Sim** para armazenar a saída gerada no arquivo de impressão, de modo que ela esteja disponível para impressão futura. Para acessar posteriormente a saída arquivada, Acesse **Administração da organização** \> **Consultas e relatórios** \> **Arquivo de relatório**.

[![Usando o destino da Impressora.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> A opção **Converter em PDF** não precisa ser ativada quando você configura o destino da **Impressora**. A conversão em PDF para fins de impressão ocorrerá mesmo que a opção seja desativada.

Para usar uma [orientação de página](electronic-reporting-destinations.md#SelectPdfPageOrientation) específica ao imprimir um documento de saída no formato Excel, você deve ativar a opção **Converter para PDF**. Quando você definir a opção **Converter para PDF** como **Sim**, o campo **Orientação da página** ficará disponível. No campo **Orientação da página**, você pode selecionar uma orientação de página.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
