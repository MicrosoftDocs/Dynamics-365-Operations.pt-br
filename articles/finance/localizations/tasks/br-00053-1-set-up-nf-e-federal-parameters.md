---
title: Configurar parâmetros federais de NF-e (Brasil)
description: É possível configurar serviços de Web da Nota Fiscal eletrônica (NF-e), códigos de rejeição e esquemas para gerar uma NF-e.
author: sndray
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d34dc520e70852f395c5a19b5347240f07ad1a2c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839739"
---
# <a name="set-up-nf-e-federal-parameters-brazil"></a>Configurar parâmetros federais de NF-e (Brasil)

[!include [banner](../../includes/banner.md)]

É possível configurar serviços de Web da Nota Fiscal eletrônica (NF-e), códigos de rejeição e esquemas para gerar uma NF-e. Após gerar uma NF-e, mensagens XML são geradas e enviadas para a Secretaria da Fazenda (SEFAZ). Esta tarefa usa a empresa de demonstração BRMF.



1. Vá para Administração da organização > Organizações > Notas fiscais eletrônicas > Parâmetros federais de NF-e.
2. Clique em Novo.
    * Uma autoridade de imposto deve ser criada por estado.  
3. No campo Autoridade, digite um valor.
4. No campo Nome, digite um valor.
5. Marque a caixa de seleção Ignorar acentos.
6. Marque a caixa de seleção Cancelar como Evento.
    * Essa opção está de acordo com o cancelamento da NF-e em eventos, em veze de um arquivo de cancelamento XML específico.  
7. Clique em Salvar.
8. Clique em Novo.
9. No campo Ambiente, selecione uma opção.
10. Selecione o serviço da Web para autorização de NF-e.
11. No campo Versão, digite um valor.
12. No campo Endereço na Internet, digite um valor.
13. Clique em Novo.
14. No campo Ambiente, selecione uma opção.
15. Selecione o serviço da Web para descarte de NF-e.
16. No campo Versão, digite um valor.
17. No campo Endereço na Internet, digite um valor.
18. Clique em Novo.
19. No campo Ambiente, selecione uma opção.
20. Selecione o serviço da Web para Consultas de NF-e.
21. No campo Versão, digite um valor.
22. No campo Endereço na Internet, digite um valor.
23. Clique em Novo.
24. No campo Ambiente, selecione uma opção.
25. Selecione o serviço da Web para devoluções de NF-e.
26. No campo Versão, digite um valor.
27. No campo Endereço na Internet, digite um valor.
28. Clique em Novo.
29. No campo Ambiente, selecione uma opção.
30. Selecione o serviço da Web para eventos de NF-e.
31. No campo Versão, digite um valor.
32. No campo Endereço na Internet, digite um valor.
33. Clique em Novo.
34. No campo Ambiente, selecione uma opção.
35. Selecione o serviço da Web para consultas de status de serviço de NF-e.
36. No campo Versão, digite um valor.
37. No campo Endereço na Internet, digite um valor.
38. Clique em Salvar.
39. Clique na guia Códigos de rejeição.
40. Clique em Novo.
    * Insira os códigos de rejeição listados no guia oficial da NF-e.  
41. No campo código de rejeição de NF-e, insira o código de rejeição do guia oficial de NF-e.
42. No campo Descrição, digite um valor.
43. Na lista, marque a linha selecionada.
44. No campo Tipo de mensagem, selecione uma opção.
45. No campo Status do documento fiscal, selecione uma opção.
    * Insira o status de nota fiscal que deve ser definido quando o código de rejeição for inserido.  
46. Clique em Salvar.
47. Clique na guia Esquemas.
48. Clique em Novo.
    * Quando aplicável, insira o caminho de arquivo XSD que será usado para validar o XML da NF-e.  
49. No campo A versão do recurso de NF-e, selecione uma opção.
50. No campo Esquema, digite um valor.
51. Clique em Novo.
52. No campo Tipo de esquema, selecione uma opção.
53. No campo A versão do recurso de NF-e, selecione uma opção.
54. No campo Esquema, digite um valor.
55. Clique em Novo.
56. No campo Tipo de esquema, selecione uma opção.
57. No campo A versão do recurso de NF-e, selecione uma opção.
58. No campo Esquema, digite um valor.
59. Clique em Novo.
60. No campo Tipo de esquema, selecione uma opção.
61. No campo A versão do recurso de NF-e, selecione uma opção.
62. No campo Esquema, digite um valor.
63. Clique em Salvar.
64. Feche a página.
65. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]