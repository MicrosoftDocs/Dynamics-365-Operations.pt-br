---
title: Processamento de documentos eletrônicos de entrada
description: Este artigo oferece uma visão geral do processamento de documentos eletrônicos recebidos.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: dec4c16c8ba9f0ba55f30f3944eff172cf9db724
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909998"
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
