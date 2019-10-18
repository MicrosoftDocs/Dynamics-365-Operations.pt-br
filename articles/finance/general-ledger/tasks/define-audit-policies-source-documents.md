---
title: Definir políticas de auditoria para documentos de origem
description: Este tópico explica como configurar e executar regras de diretiva de auditoria.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6b0fa28d778a4d9fa1f718b1d50bf1dce00be00
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186109"
---
# <a name="define-audit-policies-for-source-documents"></a>Definir políticas de auditoria para documentos de origem

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como configurar e executar regras de diretiva de auditoria. O exemplo usa relatórios de despesas com o tipo de despesa do hotel. Este procedimento usa a empresa de dados de demonstração USMF. A função do auditor contém as permissões corretas para executar essas tarefas.

1. No Painel de Navegação, vá para **Módulos > Bancada de auditoria > Configuração > Tipo de regra de política**.
2. Selecione **Novo**.
3. No campo **Nome da regra**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Nome da consulta**, selecione **Linha do relatório de despesas**
6. No campo **tipo de consulta**, selecione **Agregar**
7. No campo **Entidade legal**, selecione **Entidade legal**
8. No campo **Referência da data do documento**, selecione **Data e hora da modificação**
9. Selecione **Salvar**.
10. No Painel de Navegação, vá para **Módulos > Bancada de auditoria > Configuração > Políticas de auditoria**.
11. Selecione **Novo**.
12. No campo **Nome**, digite um valor.
13. Expanda a seção **Organizações de política**.
14. Na árvore, selecione **Contoso Entertainment System USA** e **Adicionar**.
15. Na árvore, selecione **Contoso Consulting USA** e **Adicionar**.
16. Na árvore, selecione **Contoso Retail USA** e **Adicionar**.
17. Recolha a seção **Organizações de política**.
18. Expanda a seção **Regras de política**.
19. Na lista, localize e selecione as regras de diretiva que foram criadas anteriormente.
20. Selecione **Criar regra de política**.
21. No campo **Data de efetivação**, insira uma data e hora.
22. Selecione **Filtro**.
23. Na lista, selecione a linha da **Categoria de despesa** e defina os detalhes como **Hotel**.
24. No campo **Critérios**, insira ou selecione um valor.
25. Selecione a guia **Agregar**.
26. Selecione **Adicionar**.
27. Na lista, selecione um valor de campo do **Valor da transação**.
28. No campo **Campo**, insira ou selecione um valor.
29. No campo **AggregateFunction**, selecione **Soma**.
30. Selecione a guia **Agrupar por**.
31. Selecione **Adicionar**.
32. Na lista, selecione um valor de **Funcionário**.
33. Selecione **Adicionar**.
34. Na lista, selecione um valor de **Categoria de despesa**.
35. No campo **Campo**, insira ou selecione um valor.
36. Selecione a guia **Ter**.
37. Selecione **Adicionar**.
38. Selecione **Valor da transação**.
39. No campo **Campo**, insira ou selecione um valor.
40. No campo **AggregateFunction**, selecione **Soma**.
41. No campo **Critérios**, digite `>2000`.
42. Selecione **OK**.
43. Selecione **Teste**.
44. No campo **Data de início da seleção do documento**, insira uma data e hora.
45. No campo **Data de fim da seleção do documento**, insira uma data e hora.
46. Selecione **Executar teste**.
47. No Painel de Ações, selecione **Política de auditoria**.
48. Selecione **Opções adicionais**.
49. No campo **Data inicial**, insira uma data e hora.
50. No campo **Data final**, insira uma data e hora.
51. Selecione **Lote**.
52. Expanda a seção **Executar em segundo plano**.
53. Selecione **Sim** no campo **Processamento em lotes**.
54. Selecione **OK**.
55. No Painel de Navegação, vá para **Módulos > Bancada de auditoria > Configuração > Casos de auditoria**.
56. Na lista, localize e selecione o registro desejado.
57. Expanda a seção **Associações**.
58. Na lista, localize e selecione o registro desejado.

