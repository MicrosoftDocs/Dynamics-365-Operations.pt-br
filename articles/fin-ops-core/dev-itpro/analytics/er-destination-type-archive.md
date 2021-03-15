---
title: Tipo de destino de ER do arquivo
description: Este tópico fornece informações sobre como configurar um destino de arquivo para cada componente de PASTA ou ARQUIVO de um formato de relatório eletrônico (ER).
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0067024d7a29e2a1db3b7fdba9ea3c6a63aad648
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094120"
---
# <a name="archive-er-destination-type"></a>Tipo de destino de ER do arquivo

[!include [banner](../includes/banner.md)]

Você pode configurar um destino de arquivo para cada componente de **Pasta** ou **Arquivo** de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída. Com base na configuração de destino, um documento gerado é armazenado como um anexo de um registro da lista de trabalhos do ER. Para exibir os resultados, vá para **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos de relatórios eletrônicos**.

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

> [!NOTE] 
> A estrutura ER armazena arquivos permanentemente no armazenamento de blob do Azure, ao contrário da estrutura de gerenciamento de dados, que aplica a política de retenção de sete dias para documentos que devem ser processados. Para obter mais informações, consulte [API para obter status da mensagem](../data-entities/recurring-integrations.md#api-for-getting-message-status) e [verificar API de status](../data-entities/data-management-api.md#status-check-api). Os arquivos relacionados a ER serão armazenados no armazenamento de blob do Azure como anexos de registros da tabela de aplicativos desde que sejam necessários. Um único arquivo será excluído do armazenamento de blob do Azure juntamente com o registro da tabela de aplicativos ao qual esse arquivo foi anexado.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)
- [Configurar gerenciamento de documentos](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]