---
title: Tipo de destino de ER do arquivo
description: Este tópico fornece informações sobre como configurar um destino de arquivo para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 15611a4f0000ca5ccb0ac3f4012251d5bf5689ec
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019628"
---
# <a name="ArchiveDestinationType">Local do arquivo morto</a>

[!include [banner](../includes/banner.md)]

Você pode configurar um destino de arquivo para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída. Com base na configuração de destino, um documento gerado é armazenado como um anexo de um registro da lista de trabalhos do ER.

Você pode usar essa opção para enviar o documento gerado para uma pasta do Microsoft SharePoint ou para o Armazenamento do Microsoft Azure. Definir **Habilitado** para **Sim** para enviar a saída para um destino que é definido pelo tipo de documento selecionado. Somente tipos de documento onde o grupo está definido para **Arquivo** estão disponíveis para seleção. Você define os [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento em **Administração da organização** \> **Gerenciamento de documentos** \> **Tipos de documento**. A configuração de destinos de ER é o mesma que a configuração para o sistema de gerenciamento de documentos.

[![Página Tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

O local determina onde o arquivo foi salvo. Depois que o destino do **Arquivo** for ativado, os resultado poderão ser salvos no Arquivo de trabalho. Você pode exibir os resultados em **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos arquivados de relatórios eletrônicos**.

> [!NOTE]
> Selecione um tipo de documento para o Arquivo de trabalho navegando para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico** \> **Parâmetros de relatório eletrônico**. Para obter mais informações, consulte [Configurar a estrutura do ER (Relatório eletrônico)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Você pode salvar um arquivo em uma pasta designada do SharePoint. Para definir o servidor padrão do SharePoint, vá para **Administração da organização** \> **Gerenciamento de documentos** \> **Parâmetros de gerenciamento de documentos**. Na guia **SharePoint**, configure a pasta SharePoint. Em seguida, você pode selecioná-la como a pasta na qual a saída do ER será salva. O local do **SharePoint** deve ser selecionado nesse tipo de documento.

[![Selecionando uma pasta do SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Armazenamento do Azure

Quando o local do tipo de documento é definido como **Armazenamento do Azure**, você pode salvar um arquivo no Armazenamento do Azure.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)
- [Configurar gerenciamento de documentos](../../fin-ops/organization-administration/configure-document-management.md)
