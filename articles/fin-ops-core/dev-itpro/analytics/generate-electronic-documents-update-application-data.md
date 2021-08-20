---
title: Gerar documentos eletrônicos e atualizar dados de aplicativos usando ER
description: Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo para gerar documentos eletrônicos de saída.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765799"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Gerar documentos eletrônicos e atualizar dados do aplicativo usando ER

[!include [banner](../includes/banner.md)]

Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo para gerar documentos eletrônicos de saída. Você também pode criar os formatos de ER que analisam documentos eletrônicos de entrada e usam o conteúdo desses documentos para atualizar dados de aplicativo.

Com esta funcionalidade, um único formato de ER pode ser usado para gerar documentos eletrônicos de saída e, em seguida, atualizar os dados de aplicativo. Este recurso também pode ser usado nestes cenários:

- Para evitar o uso repetido de dados de aplicativo em processos subsequentes você pode marcar os dados de aplicativo imediatamente após ser usado para gerar documentos eletrônicos. Por exemplo, você pode marcar transações de pagamento como já processadas imediatamente após terem sido incluídas em uma mensagem de pagamento gerada.
- Para armazenar os detalhes de processamento de documentos eletrônicos gerados usando a lógica de ER. Por exemplo, uma identificação exclusiva da mensagem de pagamento gerada usando a expressão de ER. A expressão é baseada nas informações inseridas na caixa de diálogo de ER quando o formato de ER é executado para gerar documentos.

Para saber mais sobre este recurso, execute o conjunto de Guias de tarefas do ER Gerar documentos com atualização de dados do aplicativo (parte do processo comercial do 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)), que o acompanham pelos detalhes de relatório e arquivamento do intrastat. Os arquivos a seguir são necessários para concluir determinadas etapas nessas Guias de tarefas. Baixe os arquivos e salve-os no seu computador local.

- [Configuração de modelo de dados de ER: Intrastat (modelo)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [Configuração de mapeamento de modelo de ER: Intrastat (mapeamento)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [Configuração de formato de ER: Intrastat (formato)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
