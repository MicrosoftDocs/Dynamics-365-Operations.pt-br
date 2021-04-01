---
title: Relatar BOMs como concluídas
description: Este artigo fornece informações sobre relatar BOMs como concluídas.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMReportFinish, BOMReportFinishMax, BOMSetupReportFinish
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef7b342ff90c066f6f2cccca08f2ec0e05cf9f8c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232269"
---
# <a name="report-boms-as-finished"></a>Relatar BOMs como concluídas

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre relatar BOMs como concluídas.

As páginas **Relatar como concluído** e **Relatório de conclusão máx.** são usadas para relatar BOMs (listas de materiais) como concluídas. Conceitualmente, o processo para relatar uma BOM como concluída é igual ao processo para relatar uma ordem de produção como concluída. Esse processo pode ser usado em, por exemplo, processos simples de montagem, onde os recursos mais avançados de ordens de produção não são necessários. A página **Relatar como concluído** permite relatar várias BOMs como concluídas em um lote. A página **Relatório máximo como concluído** permite que você relate apenas uma BOM como concluída de cada vez. A página **Relatar como concluído** está disponível a partir de um item de menu no Gerenciamento de estoques e ambas as páginas estão disponíveis como itens de menu na página **Produtos lançados**.

## <a name="report-as-finished-page"></a>Página Relatar como concluído
Se você abrir a página **Relatar como concluído** de um produto liberado,, a página sugere que você relate a quantidade padrão de estoque como concluída. Por padrão, a versão da BOM ativa será mostrada, mas é possível alterar a versão da BOM se houver outras versões aprovadas. A página também permite que você exclua registros e crie novos registros para produtos liberados que devem ser relatados como concluídos Para usar uma consulta para selecionar produtos, clique no item de menu **Selecionar**. Você pode confirmar manualmente relatar como concluído para os produtos selecionados ao clicar em **OK**. Como alternativa, você pode configurar o processo para executar em um lote. Quando o processo relatar como concluído for confirmado, o sistema gerará um diário de BOM, onde o lançamento para estoque será processado. Esse diário consiste em um item de linha para o produto concluído e uma linha de item para cada linha da BOM. É possível controlar se o diário será lançado automaticamente ou se será mantido aberto para ajustes adicionais.

## <a name="max-report-as-finished-page"></a>Máx. reportar página como concluída
Na página **Relatório de conclusão máx.**, cada linha da BOM indica o número de unidades do produto que podem ser relatadas como concluídas. Esse cálculo se baseia no estoque físico disponível de cada linha de material. No exemplo a seguir, uma peça do número de item FG consome duas peças da matéria-prima RM10 e uma peça da matéria-prima RM20. Como existem apenas 10 peças RM10 disponíveis, a quantidade máxima de FG que pode ser relatada como concluída é de cinco peças. Esse valor é mostrado no campo **Relatório de conclusão máx.**

| Nível | Nº do item | Quantidade | Disponível | Máx. Relatório de conclusão |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>BOMs com vários níveis
Quando uma BOM tiver vários níveis, você poderá controlar como os materiais são contabilizados em todos os níveis usando o campo **Detalhamento**. Esse campo está disponível na página **Relatar como concluído** e na página **Relatório de conclusão máx.** As opções a seguir estão disponíveis:

-   **Nunca** – as BOMs subjacentes não são detalhadas quando há escassez de material.
-   **Sempre** – todas as BOMs subjacentes são totalmente detalhadas. Portanto, qualquer estoque disponível para itens de componentes semiconcluídos não será usado.
-   **Escassez** – as BOMs subjacentes só serão detalhadas se a quantidade total do material desejado não estiver disponível.

### <a name="example"></a>Exemplo

Neste exemplo, três peças do produto concluído (número de item FG) estão prontas para ser relatadas como concluídas. Há uma BOM de dois níveis, como mostrado aqui.

| Nível | Nº do item | Quantidade da linha de BOM | Disponível |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

As tabelas a seguir mostram como a configuração do campo **Detalhamento** afeta o modo como as linhas do diário de BOM são geradas. **Detalhamento: Nunca**

| Nível | Nº do item | Quantidade |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

Como mostra a tabela anterior, apenas o número de item COMP é considerado deduzido no diário. O número de item RM, que faz parte do COMP, não é detalhado na linha do diário, e as duas peças em mãos do COMP não são consideradas. **Detalhamento: Sempre**

| Nível | Nº do item | Quantidade |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

Neste caso, o número de item COMP é detalhado até sua matéria-prima, número de item RM. As duas peças de COMP não são consideradas na quantidade a ser consumida por RM. **Detalhamento: Escassez**

| Nível | Nº do item | Quantidade |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

Neste caso, as duas peças disponíveis do número de item COMP são consideradas. No entanto, como três peças do número de item FG são necessárias, uma peça do número de item RM também será necessária para criar a peça adicional de COMP.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]