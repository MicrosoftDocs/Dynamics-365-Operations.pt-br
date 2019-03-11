---
title: Rastrear resultados gerados de relatórios e compará-los com os valores de linha de base
description: Este tópico fornece informações sobre como você pode comparar os resultados de relatórios de ER gerados com os valores de relatório da linha de base.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 7f7877ccaa0c45ab5f0032d6808280e3c47a43ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317927"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Rastrear resultados gerados de relatórios e compará-los com os valores de linha de base

[!include[banner](../includes/banner.md)]

Você pode rastrear os resultados dos formatos de ER que geram documentos eletrônicos de saída. Quando a geração de rastreamento estiver ativada (parâmetro do usuário do ER **Executar em modo de depuração**), um novo registro de rastreamento será gerado no log de execução do formato de ER, cada vez que um relatório de ER for executado. Os seguintes detalhes serão armazenados em cada rastreamento gerado:

- Todos os avisos gerados pelas regras de validação
- Todos os erros gerados pelas regras de validação
- Todos os arquivos gerados que são armazenados como anexos do registro de rastreamento

Você pode armazenar arquivos de aplicativo de linhas de base individuais para qualquer formato de ER. Os arquivos são considerados de linha de base quando descrevem os resultados esperados dos relatórios que estão em execução. Se um arquivo de linha de base estiver disponível para um formato ER que foi executado enquanto a geração de rastreamento estava ativada, o rastreamento armazena, além dos detalhes que foram mencionados anteriormente, o resultado da comparação do documento eletrônico gerado para o arquivo da linha de base. Em um clique, você também pode obter o documento eletrônico gerado e seu arquivo de linha de base em um arquivo zip único. Em seguida, você pode efetuar comparação detalhada usando uma ferramenta externa, como por exemplo, Windiff.

Você pode avaliar o rastreamento para analisar se os documentos eletrônicos gerados têm o conteúdo esperado. Você pode fazer essa avaliação em um ambiente de teste de aceitação do usuário (UAT) quando a base do código for alterada (por exemplo, quando você tiver migrado para uma nova instância do aplicativo, instalado pacotes de hotfix ou implantado modificações de código). Assim, você pode garantir que a avaliação não afeta a execução de relatórios de ER usados. Para muitos relatórios de ER, a avaliação poderá ser feita em modo automático.

Para saber mais sobre este recurso, execute as guias de tarefas **ER Gerar relatórios e comparar resultados (Parte 1)** e **ER Gerar relatórios e comparar resultados (Parte 2)**, que fazem parte do processo de negócios **7.5.4.3 Testar serviços/soluções de TI (10679)** e podem ser baixados do [Centro de Download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Essas guias de tarefas o direcionam pelo processo de configuração da estrutura de ER para usar arquivos da linha de base para avaliar documentos eletrônicos gerados.
