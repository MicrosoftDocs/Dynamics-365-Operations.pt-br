---
title: Processamento de documentos eletrônicos de entrada
description: Este artigo oferece uma visão geral do processamento de documentos eletrônicos recebidos.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 554bc8fde3b2135eb878d885541c76ecd6d66493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277291"
---
# <a name="processing-of-incoming-electronic-documents"></a>Processamento de documentos eletrônicos de entrada

[!include [banner](../includes/banner.md)]

Documentos eletrônicos recebidos, como faturas eletrônicas de fornecedores, podem ser importados e processados de duas maneiras:

- Os arquivos são recuperados de canais externos e passados diretamente para o aplicativo conectado. Nela, elas passam por transformações adicionais e são importadas para o banco de dados.
- Os arquivos passam no pré-processamento no serviço de faturamento eletrônico e, em seguida, são passados para seu aplicativo conectado.

O faturamento eletrônico oferece suporte a dois canais para documentos de entrada: email e pastas do Microsoft SharePoint.

Há dois tipos de configuração para especificar se os documentos estão sendo processados ou se são passados diretamente para o aplicativo conectado:

- **Canal de dados** – O sistema passará o documento diretamente para o aplicativo conectado.
- **Canal de dados com pipeline de processamento** – Você pode configurar ações adicionais que serão executadas antes que o documento seja passado para o aplicativo conectado.

Para obter informações sobre como configurar os cenários para o processamento de documentos eletrônicos de entrada para os canais distintos, consulte [Configurar um canal de email](e-invoicing-configure-email.md) e [Configurar um canal do SharePoint](e-invoicing-configure-sharepoint-channel.md).
