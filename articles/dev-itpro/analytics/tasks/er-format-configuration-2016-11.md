--- 
title: "Criar configurações de formato para relatórios eletrônicos (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 8c11f64fd899b8be4e6c3179913787eb2c32c6c6
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-electronic-reporting-er-format-configurations"></a>Criar configurações de formato para relatórios eletrônicos (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE). Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos. Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "mapear modelo para as fontes de dados selecionadas".


## <a name="create-a-new-format-configuration"></a>Criar uma nova configuração de formato
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, selecione 'Pagamentos (modelo simplificado)'.
4. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
5. No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.
6. No campo Nome, digite 'BACS (Reino Unido fictício)'.
    * BACS (Reino Unido fictício)  
7. No campo Descrição, digite 'Formato de pagamento de fornecedor BACS (Reino Unido fictício)'.
    * Formato de pagamento de fornecedor BACS (Reino Unido fictício)  
    * O provedor de configuração ativo é automaticamente inserido aqui. Este provedor será capaz de manter essa configuração. Outros provedores podem usar esta configuração, mas não poderão mantê-la.  
    * Um formato específico de documento eletrônico pode ser definido. Deixe este campo em branco se desejar selecionar um formato durante a execução.  
8. No campo Definição do modelo de dados, insira ou selecione um valor.
9. Clique em Criar configuração.
    * Uma nova configuração foi criada. A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.  

## <a name="design-format-of-electronic-document"></a>Projetar formato de documento eletrônico
1. Clique em Designer.
2. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione 'Comum\Arquivo'.
4. No campo Nome, digite 'Xml'.
    * Xml  
5. No campo Codificação, digite 'UTF-8'.
    * UTF-8  
6. Clique em OK.
7. Clique em Adicionar para abrir a caixa de diálogo suspensa.
8. Na árvore, selecione 'XML\Elemento'.
9. No campo Nome, digite 'Mensagem'.
    * Mensagem  
10. Clique em OK.
11. Na árvore, selecione "Xml\Mensagem".
12. Clique em Adicionar elemento.
13. No campo Nome, digite 'ProcessingDate'.
    * ProcessingDate  
14. Clique em OK.
15. Clique em Adicionar elemento.
16. No campo Nome, digite 'MessageId'.
    * MessageId  
17. Clique em OK.
18. Clique em Adicionar elemento.
19. No campo Nome, digite 'Pagamentos'.
    * Pagamentos  
20. Clique em OK.
21. Na árvore, selecione "Xml\Mensagem\Pagamentos".
22. Clique em Adicionar elemento.
23. No campo Nome, digite 'Item'.
    * Item  
24. Clique em OK.
25. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".
26. Clique em Adicionar para abrir a caixa de diálogo suspensa.
27. Na árvore, selecione 'XML\Atributo'.
28. No campo Nome, digite 'Id'.
    * ID  
29. Clique em OK.
30. Clique em Adicionar para abrir a caixa de diálogo suspensa.
31. Na árvore, selecione 'XML\Elemento'.
32. No campo Nome, digite 'Fornecedor'.
    * Fornecedor  
33. Clique em OK.
34. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor".
35. Clique em Adicionar elemento.
36. No campo Nome, digite 'Nome'.
    * Nome  
37. Clique em OK.
38. Clique em Adicionar elemento.
39. No campo Nome, digite 'Banco'.
    * Banco  
40. Clique em OK.
41. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".
42. Clique em Adicionar elemento.
43. No campo Nome, digite 'Número Identificador do banco'.
    * Número identificador do banco  
44. Clique em OK.
45. Clique em Adicionar elemento.
46. No campo Nome, digite 'NúmeroConta'.
    * AccountNumber  
47. Clique em OK.
48. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor".
49. Clique em Copiar.
50. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".
51. Clique em Colar.
52. No campo Nome, digite 'Pagador'.
    * Pagador  
53. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".
54. Clique em Adicionar elemento.
55. No campo Nome, digite 'Moeda'.
    * Moeda  
56. Clique em OK.
57. Clique em Adicionar elemento.
58. No campo Nome, digite 'Descrição'.
    * descrição  
59. Clique em OK.
60. Clique em Adicionar elemento.
61. No campo Nome, digite 'TransDate'.
    * TransDate  
62. Clique em OK.
63. Clique em Adicionar elemento.
64. No campo Nome, digite 'Valor'.
    * Valor  
65. Clique em OK.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Preparar os componentes do formato para mapeamento aos elementos do modelo de dados
1. Na árvore, selecione "Xml\Mensagem\ProcessingDate".
2. Clique em Adicionar para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione "Texto\DateTime"
4. No campo Formato, digite 'aaaa-MM-dd'.
    * dd-MM-aa  
5. Clique em OK.
6. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\TransDate".
7. Clique em Adicionar DateTime.
8. No campo Formato, digite 'aaaa-MM-dd'.
    * dd-MM-aa  
9. No campo DateTime, selecione "Data".
10. Clique em OK.
11. Na árvore, selecione "Xml\Mensagem\MessageId".
12. Clique em Adicionar para abrir a caixa de diálogo suspensa.
13. Na árvore, selecione 'Texto\Cadeia de caracteres'.
14. Clique em OK.
15. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome".
16. Clique em Adicionar cadeia de caracteres
17. Clique em OK.
18. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\RoutingNumber".
19. Clique em Adicionar cadeia de caracteres
20. Clique em OK.
21. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\AccountNumber".
22. Clique em Adicionar cadeia de caracteres
23. Clique em OK.
24. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Nome".
25. Clique em Adicionar cadeia de caracteres
26. Clique em OK.
27. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\RoutingNumber".
28. Clique em Adicionar cadeia de caracteres
29. Clique em OK.
30. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\AccountNumber".
31. Clique em Adicionar cadeia de caracteres
32. Clique em OK.
33. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Moeda".
34. Clique em Adicionar cadeia de caracteres
35. Clique em OK.
36. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Descrição".
37. Clique em Adicionar cadeia de caracteres
38. Clique em OK.
39. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Valor".
40. Clique em Adicionar cadeia de caracteres
41. Clique em OK.
42. Clique em Salvar.
43. Feche a página.


