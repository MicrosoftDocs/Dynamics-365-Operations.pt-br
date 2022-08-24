---
title: Transmissão automática de notas fiscais eletrônicas (Brasil)
description: Use o procedimento a seguir para configurar parâmetros de email para enviar automaticamente uma Nota Fiscal eletrônica (NF-e) a um fornecedor ou um cliente após sua aprovação ou cancelamento, ou se você gerar uma carta de correção.
author: AdamTrukawka
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.search.industry: Manufacturing;Distribution;Service industries
ms.openlocfilehash: 7f6847129d5b9bdc6ac0cefc64a7fefe1efcc860
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282385"
---
# <a name="automatic-transmission-of-nf-e-fiscal-documents-brazil"></a>Transmissão automática de notas fiscais eletrônicas (Brasil)

[!include [banner](../../includes/banner.md)]

Use o procedimento a seguir para configurar parâmetros de email para enviar automaticamente uma Nota Fiscal eletrônica (NF-e) a um fornecedor ou um cliente após sua aprovação ou cancelamento, ou se você gerar uma carta de correção. Você pode configurar um grupo de lotes e modelos de e-mail para uma NF-e. Você deve criar modelos de e-mail separados para uma NF-e aprovada, uma NF-e cancelada e uma carta de correção. Então será possível criar um processo em lote para enviar a NF-e por email. Esta tarefa usa a empresa de demonstração BRMF.

1. Acesse Administração do sistema > Configuração > Grupo de lotes.
2. Clique em Novo.
3. No campo Grupo, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Feche a página.
7. Acesse Administração do sistema > Tarefas periódicas > Processamento de email > Lote.
8. Expanda a seção Executar em segundo plano.
9. Selecione Sim no campo Processamento de lote.
10. No campo Grupo de lotes, insira ou selecione um valor.
11. Clique em Recorrência.
12. Selecione a opção Nenhuma data de término.
13. No campo Contagem, insira um número.
14. No campo Fuso horário, selecione uma opção.
15. Clique em OK.
16. Clique em OK.
17. Acesse Administração da organização > Configuração > Modelos de email.
18. Clique em Novo.
19. No campo ID do email, digite um valor.
20. No campo Email do remetente, digite um valor.
21. No campo Nome do remetente, digite um valor.
22. No campo Código do idioma padrão, insira ou selecione um valor.
23. No campo Linhas ou cabeçalho, selecione uma opção.
24. No campo Grupo de lotes, insira ou selecione um valor.
25. No campo Descrição de email, digite um valor.
26. No campo Linhas ou cabeçalho, selecione uma opção.
27. Clique em Salvar.
28. Na lista, marque a linha selecionada.
29. No campo Assunto, digite um valor.
30. No campo Idioma, insira ou selecione um valor.
31. Clique em Editar.
32. No campo WritableContent, digite um valor.
33. Clique em OK.
34. Clique em Salvar.
35. Feche a página.
36. Feche a página.
37. Acesse Administração da organização > Organizações > Estabelecimentos fiscais > Estabelecimentos fiscais.
38. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo ID do estabelecimento fiscal com um valor de "Matriz".
39. Expanda a seção NF-e e NFC-e federal.
40. Clique em Editar.
41. No campo NF-e aprovada, insira ou selecione um valor.
42. Selecione Sim no campo Anexar DANFE em PDF ao email.
43. Clique em Salvar.
44. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
