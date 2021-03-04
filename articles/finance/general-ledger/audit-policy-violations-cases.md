---
title: Auditar violações de política e casos
description: O artigo explica como os casos de auditoria são gerados de violações de regras de diretiva de auditoria. Também inclui informações sobre as diversas maneiras das políticas de auditoria usarem o intervalo de datas de seleção de documento.
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d14894d331037033b27fac3fd7ff98c5521eaf98
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440309"
---
# <a name="audit-policy-violations-and-cases"></a>Auditar violações de política e casos

[!include [banner](../includes/banner.md)]

O artigo explica como os casos de auditoria são gerados de violações de regras de diretiva de auditoria. Também inclui informações sobre as diversas maneiras das políticas de auditoria usarem o intervalo de datas de seleção de documento.

<a name="how-audit-cases-are-generated"></a>Como os casos de auditoria são gerados
-----------------------------

As políticas de auditoria são usadas para identificar relatórios de despesas, ordens de compra e faturas de fornecedor que não estão de acordo com as regras comerciais que você define e configura como regras de política de auditoria. 

As políticas de auditoria são executadas em modo de lotes. Quando você executa uma política de auditoria, todas as regras de política que fazem parte dela são executadas ao mesmo tempo.

Cada regra de política avalia um conjunto de documentos. A regra de política seleciona documentos que estão no intervalo de datas de seleção de documento e que correspondem aos critérios especificados. Por exemplo, uma regra de política pode selecionar os relatórios de despesas com refeições acima de 50,00. Outra regras de política podem selecionar faturas de fornecedor que podem ser pagas para um fornecedor específico. Para cada documento selecionado na definição, uma violação é gerada. Essa violação é um registro de que um documento específico, como uma fatura 12345, não atende às regras de política. 

Vários registros de violação de auditoria são agrupados e associados a casos de auditoria. Por padrão, os casos de cada política de auditoria são agrupados por regra de política de auditoria. Se você preferir, selecione outros critérios de agrupamento ao usar a página **Critérios de agrupamento de caso**. Por exemplo, você pode agrupar os cabeçalhos de despesas pela ID do projeto e faturas por conta do fornecedor. Nesse caso, todas as violações do cabeçalho de despesas que têm a mesma ID do projeto serão agrupadas nos mesmos caso e todas as faturas de fornecedores que têm a mesma conta de fornecedor serão agrupadas no mesmo caso. 

> [!NOTE]
> Para as regras de política com base em um tipo de consulta **Duplicar**, as violações não são agrupadas por regra de política ou pelo critério especificado na página **Critérios de agrupamento de caso**. Em vez de isso, são agrupados pelos critérios criados na regra de política de auditoria. Por exemplo, se uma regra de política avaliar relatórios de despesas em busca de despesas duplicadas de mesmo valor, ID do mercado e data, todas as despesas que têm os mesmos valores nesses campos seriam um caso. As despesas que têm valores diferentes serão um caso separado.

Depois que os casos de auditoria foram gerados, serão processados usando os processos típicos do gerenciamento dos casos.

## <a name="document-selection-date-ranges"></a>Intervalos de datas para seleção de documento
Quando uma política de auditoria for executada, cada regras de política seleciona os documentos do tipo especificado que têm uma data dentro do intervalo de datas de seleção de documento. O intervalo de datas de seleção de documentos é especificado na página **Opções adicionais**. Vários documentos têm mais de uma data associada a eles. O campo de data que a regra de política de auditoria usa é especificado na página **Tipo de regras de política**.

Veja aqui outras formas que a política de auditoria usa o intervalo de datas da seleção de documentos:

-   A política usa a versão de cada regra de política que estará em vigor no último dia do intervalo de datas de seleção de documentos. Você pode visualizar as datas para cada regra de política na página da lista **Políticas de auditoria**.
-   A política usa os nós de organização que são associados à política no último dia do intervalo de datas de seleção de documento. Somente os nós da organização que são associados à política são exibidos na página da lista **Políticas de auditoria**.
-   Para as regras de política se baseiam em um tipo de consulta **Pesquisa da lista**, a política avalia documentos para entidades monitoradas em vigor no último dia do intervalo de datas de seleção de documento.


Para obter mais informações, consulte [Auditar regras da política](audit-policy-rules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]