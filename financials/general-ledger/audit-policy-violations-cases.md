---
title: "Auditar violações de política e casos"
description: "O artigo explica como os casos de auditoria são gerados de violações de regras de diretiva de auditoria. Também inclui informações sobre as diversas maneiras das políticas de auditoria usarem o intervalo de datas de seleção de documento."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: 77f72c9414f1fad720055e58e3f704b9c713072f
ms.lasthandoff: 03/31/2017


---

# <a name="audit-policy-violations-and-cases"></a>Auditar violações de política e casos

O artigo explica como os casos de auditoria são gerados de violações de regras de diretiva de auditoria. Também inclui informações sobre as diversas maneiras das políticas de auditoria usarem o intervalo de datas de seleção de documento.

<a name="how-audit-cases-are-generated"></a>Como os casos de auditoria são gerados
-----------------------------

As políticas de auditoria são usadas para identificar relatórios de despesas, ordens de compra e faturas de fornecedor que não estão de acordo com as regras comerciais que você define e configura como regras de política de auditoria. 

As políticas de auditoria são executadas em modo de lotes. Quando você executa uma política de auditoria, todas as regras de política que fazem parte dela são executadas ao mesmo tempo.

Cada regra de política avalia um conjunto de documentos. A regra de política seleciona documentos que estão no intervalo de datas de seleção de documento e que correspondem aos critérios especificados. Por exemplo, uma regra de política pode selecionar os relatórios de despesas com refeições acima de 50,00. Outra regras de política podem selecionar faturas de fornecedor que podem ser pagas para um fornecedor específico. Para cada documento selecionado na definição, uma violação é gerada. Essa violação é um registro de que um documento específico, como uma fatura 12345, não atende às regras de política. 

Vários registros de violação de auditoria são agrupados e associados a casos de auditoria. Por padrão, os casos de cada política de auditoria são agrupados por regra de política de auditoria. Se você preferir, selecione outros critérios de agrupamento ao usar a página **Critérios de agrupamento de caso**. Por exemplo, pode agrupas cabeçalhos de despesas por ID e por notas fiscais de fornecedor de projeto por conta de fornecedor. Nesse caso, todas as violações de cabeçalho de despesa com a mesma ID de projeto serão agrupadas mesmo engradado em, e todas as notas fiscais de fornecedor com a mesma conta de fornecedor serão agrupadas no mesmo engradado. 

> [!NOTE]
> Para as regras de diretiva de auditoria baseadas em ** duplicados ** tipo de consulta, as violações não são agrupadas por regras de diretiva ou os critérios especificados ** engradado que agrupam ** critérios na página. Em vez de isso, são agrupados pelos critérios criados na regra de política de auditoria. Por exemplo, se uma regra de política avaliar relatórios de despesas em busca de despesas duplicadas de mesmo valor, ID do mercado e data, todas as despesas que têm os mesmos valores nesses campos seriam um caso. As despesas que têm valores diferentes serão um caso separado.

Depois que os casos de auditoria foram gerados, serão processados usando os processos típicos do gerenciamento dos casos.

## <a name="document-selection-date-ranges"></a>Intervalos de datas para seleção de documento
Quando uma política de auditoria for executada, cada regras de política seleciona os documentos do tipo especificado que têm uma data dentro do intervalo de datas de seleção de documento. O intervalo de datas de seleção de documentos é especificado na página **Opções adicionais**. Vários documentos têm mais de uma data associada a eles. O campo de data que a regra de política de auditoria usa é especificado na página **Tipo de regras de política**.

Veja aqui outras formas que a política de auditoria usa o intervalo de datas da seleção de documentos:

-   A política usa a versão de cada regra de política que estará em vigor no último dia do intervalo de datas de seleção de documentos. Você pode visualizar as datas para cada regra de política na página da lista **Políticas de auditoria**.
-   A política usa os nós de organização que são associados à política no último dia do intervalo de datas de seleção de documento. Somente os nós da organização que são associados à política são exibidos na página da lista **Políticas de auditoria**.
-   Para as regras de política se baseiam em um tipo de consulta **Pesquisa da lista**, a política avalia documentos para entidades monitoradas em vigor no último dia do intervalo de datas de seleção de documento.


Para obter mais informações, consulte [] regras de diretiva de auditoria (audit-policy-rules.md)


