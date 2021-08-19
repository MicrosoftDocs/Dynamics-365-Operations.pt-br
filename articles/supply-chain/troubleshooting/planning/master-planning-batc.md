---
title: Você não pode filtrar itens de planejamento mestre por seus valores de grupo de cobertura relacionados
description: Você não pode filtrar itens de planejamento mestre por seus valores de grupo de cobertura relacionados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9750a73f0962179512c5e21a614a276c313ff975b7494f31589ca936886ecf6e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781384"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Você não pode filtrar itens de planejamento mestre por seus valores de grupo de cobertura relacionados

Número da base de dados de conhecimento: 4612572

## <a name="symptoms"></a>Sintomas

Você deseja filtrar os itens que serão incluídos em um trabalho em lote de planejamento mestre, com base nos valores dos registros relacionados da tabela de cobertura do item. (Por exemplo, você deseja filtrar itens por seu valor **Fornecedor** e/ou **Grupo de cobertura**). A configuração do filtro para o trabalho em lote permite criar uma junção da tabela **Itens** à tabela **Cobertura de item** e, em seguida, especificar valores de campo da tabela de cobertura de item em sua consulta. Contudo, depois de concluir essa configuração, o sistema ainda cria ordens planejadas para toda a cobertura do item, não apenas para os itens que correspondem aos valores de campo especificados da tabela de cobertura do item.

## <a name="resolution"></a>Resolução

O filtro de trabalho em lote pode filtrar somente em itens. Embora você possa adicionar uma junção à tabela **Cobertura de item**, as configurações de filtro feitas nessa tabela não afetarão a saída da consulta. Em tempo de execução, o sistema executa o planejamento para todos os grupos de cobertura e todas as variações que os itens filtrados possuem. Depois que um item já está incluído na execução, qualquer grupo de cobertura incluído no filtro de item não afetarão a saída de planejamento.
