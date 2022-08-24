---
title: ER Criar uma configuração de formato (Novembro de 2016)
description: Este artigo explica como criar uma configuração de formato para relatórios eletrônicos (ER).
author: kfend
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
ms.openlocfilehash: 3c705add64a46c4cce5127f16fae45edba1bc001
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290714"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER Criar uma configuração de formato (Novembro de 2016)

[!include [banner](../../includes/banner.md)]

Este artigo explica como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (ER). Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos. Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "Mapear modelo para as fontes de dados selecionadas".


## <a name="create-a-new-format-configuration"></a>Criar uma nova configuração de formato
1. Vá par **Administração da organização > Espaços de trabalho > Relatório eletrônico**.
2. Clique em **Configurações de relatórios**.
3. Na árvore, selecione **Pagamentos (modelo simplificado)**.
4. Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.

 > [!NOTE]
 > Se não aparecer **Criar configuração**, você deverá habilitar o modo de design na página **Parâmetros de relatório eletrônico**. 
 
5. No campo **Novo**, insira **Formato baseado no modelo de dados PaymentModel**.
6. No campo **Nome**, digite **BACS (Reino Unido fictício)**.
7. No campo **Descrição**, digite **Formato de pagamento de fornecedor BACS (Reino Unido fictício)**.
    * O provedor de configuração ativo é automaticamente inserido aqui. Este provedor será capaz de manter essa configuração. Outros provedores podem usar esta configuração, mas não poderão mantê-la.  
    * Um formato específico de documento eletrônico pode ser definido. Deixe este campo em branco se desejar selecionar um formato durante a execução.  
8. No campo **Definição do modelo de dados**, insira ou selecione um valor.
9. Clique em **Criar configuração**. Uma nova configuração foi criada. A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.  

## <a name="design-the-format-of-an-electronic-document"></a>Projetar o formato de um documento eletrônico
1. Clique em **Designer**.
2. Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione **Comum\Arquivo**.
4. No campo **Nome**, digite **Xml**.
5. No campo **Codificação**, digite **UTF-8**.
6. Clique em **OK**.
7. Clique em **Adicionar**.
8. Na árvore, selecione **XML\Elemento**.
9. No campo **Nome**, digite **Mensagem**.
10. Clique em **OK**.
11. Na árvore, selecione **Xml\Mensagem**.
12. Clique em **Adicionar Elemento**.
13. No campo **Nome**, digite **ProcessingDate**.
14. Clique em **OK**.
15. Clique em **Adicionar Elemento**.
16. No campo Nome, digite **MessageId**.
17. Clique em **OK**.
18. Clique em **Adicionar Elemento**.
19. No campo **Nome**, digite **Pagamentos**.
20. Clique em **OK**.
21. Na árvore, selecione **Xml\Message\Payments**.
22. Clique em **Adicionar Elemento**.
23. No campo **Nome**, digite **Item**.
24. Clique em **OK**.
25. Na árvore, selecione **Xml\Message\Payments\Item**.
26. Clique em **Adicionar**.
27. Na árvore, selecione **XML\Attribute**.
28. No campo Nome, digite **Id**.
29. Clique em **OK**.
30. Clique em **Adicionar**.
31. Na árvore, selecione **XML\Elemento**.
32. No campo Nome, digite **Fornecedor**.
33. Clique em **OK**.
34. Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.
35. Clique em **Adicionar Elemento**.
36. No campo Nome, digite **Nome**.
37. Clique em **OK**.
38. Clique em **Adicionar Elemento**.
39. No campo **Nome**, digite **Banco**.
40. Clique em **OK**.
41. Na árvore, selecione **Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco**.
42. Clique em **Adicionar Elemento**.
43. No campo **Nome**, digite **RoutingNumber**.
44. Clique em **OK**.
45. Clique em **Adicionar Elemento**.
46. No campo **Nome**, digite **AccountNumber**.
47. Clique em **OK**.
48. Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.
49. Clique em **Copiar**.
50. Na árvore, selecione **Xml\Message\Payments\Item**.
51. Clique em **Colar**.
52. No campo **Nome**, digite **Pagador**.
53. Na árvore, selecione **Xml\Message\Payments\Item**.
54. Clique em **Adicionar Elemento**.
55. No campo **Nome**, digite **Moeda**.
56. Clique em **OK**.
57. Clique em **Adicionar Elemento**.
58. No campo **Nome**, digite **Descrição**.
59. Clique em **OK**.
60. Clique em **Adicionar Elemento**.
61. No campo Nome, digite **TransDate**.
62. Clique em **OK**.
63. Clique em **Adicionar Elemento**.
64. No campo Nome, digite **Valor**.
65. Clique em **OK**.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Preparar os componentes do formato para mapeamento aos elementos do modelo de dados
1. Na árvore, selecione **Xml\Message\ProcessingDate**.
2. Clique em **Adicionar** para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione **Texto\DateTime**.
4. No campo **Formato**, digite **aaaa-MM-dd**.
5. Clique em **OK**.
6. Na árvore, selecione **Xml\Message\Payments\Item\TransDate**.
7. Clique em **Adicionar DateTime.**
8. No campo **Formato**, digite **aaaa-MM-dd**.
9. No campo do tipo **DateTime**, selecione **Data**.
10. Clique em **OK**.
11. Na árvore, selecione **Xml\Message\MessageId**.
12. Clique em **Adicionar** para abrir a caixa de diálogo suspensa.
13. Na árvore, selecione **Texto\Cadeia de caracteres**.
14. Clique em **OK**.
15. Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Name**.
16. Clique em **Adicionar cadeia de caracteres**.
17. Clique em **OK**.
18. Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.
19. Clique em **Adicionar cadeia de caracteres**.
20. Clique em **OK**.
21. Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.
22. Clique em **Adicionar cadeia de caracteres**.
23. Clique em **OK**.
24. Na árvore, selecione **Xml\Message\Payments\Item\Payer\Name**.
25. Clique em **Adicionar cadeia de caracteres**.
26. Clique em **OK**.
27. Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.
28. Clique em **Adicionar cadeia de caracteres**.
29. Clique em **OK**.
30. Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.
31. Clique em **Adicionar cadeia de caracteres**.
32. Clique em **OK**.
33. Na árvore, selecione **Xml\Message\Payments\Item\Currency**.
34. Clique em **Adicionar cadeia de caracteres**.
35. Clique em **OK**.
36. Na árvore, selecione **Xml\Message\Payments\Item\Description**.
37. Clique em **Adicionar cadeia de caracteres**.
38. Clique em **OK**.
39. Na árvore, selecione **Xml\Message\Payments\Item\Amount**.
40. Clique em **Adicionar cadeia de caracteres**.
41. Clique em **OK**.
42. Clique em **Salvar**.
43. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
