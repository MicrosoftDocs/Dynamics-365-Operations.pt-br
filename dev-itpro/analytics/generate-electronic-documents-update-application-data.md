---
title: "Gerar documentos eletrônicos e atualizar dados de aplicativo usando a ferramenta de relatórios eletrônicos"
description: "Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo do Finance and Operations para gerar documentos eletrônicos de saída. Você também pode criar os formatos de ER que analisam documentos eletrônicos de entrada e usam o conteúdo desses documentos para atualizar dados de aplicativo."
author: kfend
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: Lifecycle Services
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.2, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d37d20b26d8ae755a6c5a688afd1ad0541d1f693
ms.openlocfilehash: 7e4e0acb374fe091c0e099355204116345c62997
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---


Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo do Finance and Operations para gerar documentos eletrônicos de saída. Você também pode criar os formatos de ER que analisam documentos eletrônicos de entrada e usam o conteúdo desses documentos para atualizar dados de aplicativo. 

Com esta funcionalidade, um único formato de ER pode ser usado para gerar documentos eletrônicos de saída e, em seguida, atualizar os dados de aplicativo. Este recurso também pode ser usado nestes cenários:

- Para evitar o uso repetido de dados de aplicativo em processos subsequentes você pode marcar os dados de aplicativo imediatamente após ser usado para gerar documentos eletrônicos. Por exemplo, você pode marcar transações de pagamento como já processadas imediatamente após terem sido incluídas em uma mensagem de pagamento gerada.
- Para armazenar os detalhes de processamento de documentos eletrônicos gerados usando a lógica de ER. Por exemplo, uma identificação exclusiva da mensagem de pagamento gerada usando a expressão de ER. A expressão é baseada nas informações inseridas na caixa de diálogo de ER quando o formato de ER é executado para gerar documentos.

Para saber mais sobre este recurso, execute o conjunto de Guias de tarefas do ER Gerar documentos com atualização de dados do aplicativo (parte do processo comercial do 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)), que o acompanham pelos detalhes de relatório e arquivamento do intrastat. Os arquivos a seguir são necessários para concluir determinadas etapas nessas Guias de tarefas. Baixe os arquivos e salve-os no seu computador local.

- [Configuração de modelo de dados de ER: Intrastat (modelo)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configuração de mapeamento de modelo de ER: Intrastat (mapeamento)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configuração de formato de ER: Intrastat (formato)](https://go.microsoft.com/fwlink/?linkid=849038)

