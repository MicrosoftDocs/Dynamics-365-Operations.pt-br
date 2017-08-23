--- 
title: "Definir políticas de auditoria para documentos de origem"
description: Este procedimento mostra como configurar e executar regras de diretiva de auditoria.
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ca4c8735258170c41dc907ed0ef8afca250ea9dd
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Definir políticas de auditoria para documentos de origem

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar e executar regras de diretiva de auditoria. O exemplo usa relatórios de despesas com o tipo de despesa do hotel. Este procedimento usa a empresa de dados de demonstração USMF. A função do auditor contém as permissões corretas para executar essas tarefas.

1. Vá para Bancada de auditoria > Configuração > Tipo de regra de política.
2. Clique em Novo.
3. No campo Nome da regra, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo nome da consulta, selecione Linha do relatório de despesas
6. No campo Tipo de consulta, selecione Agregar
7. No campo Entidade legal, selecione uma Entidade legal.
8. No campo de referência da data do documento, selecione a data e a hora da modificação
9. Clique em Salvar.
10. Vá para Bancada de auditoria > Configuração > Políticas de auditoria.
11. Clique em Novo.
12. No campo Nome, digite um valor.
13. Expanda a seção de organizações de diretivas.
14. Na árvore, selecione 'Contoso Entertainment System USA'.
15. Clique em Adicionar.
16. Na árvore, selecione 'Contoso Consulting USA'.
17. Clique em Adicionar.
18. Na árvore, selecione 'Contoso Retail USA'.
19. Clique em Adicionar.
20. Recolha a seção de organizações de diretivas.
21. Expanda a seção de regras de diretivas.
22. Na lista, localize e selecione as regras de diretiva que foram criadas anteriormente.
23. Clique em Criar regra de política.
24. No campo de data efetiva, insira uma data e hora.
25. Clique em Filtro.
26. Na lista, selecione a linha para a categoria de despesa, e defina os detalhes ao hotel
27. No campo Critérios, insira ou selecione um valor.
28. Clique na guia Agregado.
29. Clique em Adicionar.
30. Na lista, selecione um valor de campo do valor da transação
31. No campo Campo, insira ou selecione um valor.
32. No campo de AggregateFunction, selecione 'Soma'.
33. Clique no Grupo por Guia.
34. Clique em Adicionar.
35. Na lista, selecione um valor de Funcionário  
36. Clique em Adicionar.
37. Na lista, selecione um valor de Categoria de despesa
38. No campo Campo, insira ou selecione um valor.
39. Clique na guia Ter.
40. Clique em Adicionar.
41. Selecione o valor da transação
42. No campo Campo, insira ou selecione um valor.
43. No campo de AggregateFunction, selecione 'Soma'.
44. No campo Critérios, digite ">2000".
45. Clique em OK.
46. Clique em Teste.
47. No campo Data de início da seleção do documento, insira uma data e hora.
48. No campo Data de fim da seleção do documento, insira uma data e hora.
49. Clique em Executar teste.
50. No Painel de Ação, clique em Auditar política.
51. Clique em Opções adicionais.
52. No campo de data Iniciar, insira uma data e hora.
53. No campo de data Finalizar, insira uma data e hora.
54. Clique em Lote.
55. Expanda a seção Executar em segundo plano.
56. Selecione Sim no campo Processamento de lote.
57. Clique em OK.
58. Vá para Bancada de auditoria > Casos de auditoria.
59. Na lista, localize e selecione o PDV desejado.
60. Na lista, clique no link na linha selecionada.
61. Expanda a seção Associações.
62. Na lista, localize e selecione o PDV desejado.
63. Na lista, clique no link na linha selecionada.


