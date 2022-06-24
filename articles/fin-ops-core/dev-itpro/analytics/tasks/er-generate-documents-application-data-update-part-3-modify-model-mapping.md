---
title: Modificar modelos e mapeamentos para gerar documentos com dados da solicitação de emprego
description: Este artigo descreve como criar configurações de relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo. (Parte 2 - Gerar documentos).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 797057112e9476389655b870fd729acd33d57e43
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908287"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>Modificar modelos e mapeamentos para gerar documentos com dados da solicitação de emprego

[!include [banner](../../includes/banner.md)]

Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 2: Gerar documentos)". 

As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo. Nesse procedimento, você modificará as configurações de ER para começar a usá-las para gerar documentos eletrônicos e dados de aplicativo de atualização. Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.


## <a name="modify-data-model"></a>Modifique o modelo de dados
1. Acesse Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, selecione 'Intrastat (model)'.
    * Você estenderá como usa o modelo de dados. Além de usá-lo como a fonte de dados para gerar o relatório Intrastat, o modelo de dados será usado para obter detalhes sobre o processo de relatório Intrastat. Os detalhes serão usados para atualizar dados do aplicativo.   
3. Clique em Designer.
4. Clique em Novo para abrir a caixa de diálogo suspensa.
5. No campo Novo nó como um, insira "Raiz do modelo".
6. No campo Nome, digite 'Para atualização de dados do aplicativo'.
    * Para atualização de dados do aplicativo  
7. Clique em Adicionar.
8. Na árvore, selecione 'Para atualização de dados do aplicativo'.
    * Este novo item raiz foi adicionado para especificar o fluxo de dados para mover dados do relatório Intrastat (usado como uma fonte de dados) para as tabelas de aplicativo (o destino de atualização). Observe que diferentes itens raiz devem ser usados para receber dados que são lançados no documento de saída e receber dados do documento usado para atualizar dados do aplicativo.   
9. Clique em Novo para abrir a caixa de diálogo suspensa.
10. No campo Nome, digite 'Cabeçalho do arquivo-morto'.
    * Cabeçalho do arquivo-morto  
11. No campo Tipo de item, selecione 'Lista de Registro'.
12. Clique em Adicionar.
    * Conforme você cria um registro para cada relatório Intrastat que é gerado, você deve criar um novo item para tal.  
13. Clique em Novo para abrir a caixa de diálogo suspensa.
14. No campo Nome, digite 'Nome do arquivo'.
    * Nome do arquivo  
15. No campo Tipo de item, selecione 'String'.
16. Clique em Adicionar.
17. Clique em Novo para abrir a caixa de diálogo suspensa.
18. No campo Nome, digite 'Número de linhas'.
    * Número de linhas  
19. No campo Tipo de item, selecione 'Inteiro'.
20. Clique em Adicionar.
    * Adicione este item para representar o número das transações Intrastat que são informadas durante o processo de relatório atual.  
21. Clique em Novo para abrir a caixa de diálogo suspensa.
22. No campo Nome, digite 'Arquivar linhas'.
    * Arquivar linhas  
23. No campo Tipo de item, selecione 'Lista de Registro'.
24. Clique em Adicionar.
    * Adicione este item para representar a lita de das transações Intrastat que são informadas durante o processo de relatório atual.  
25. Clique em Novo para abrir a caixa de diálogo suspensa.
26. No campo Nome, digite 'Valor'.
    * Valor  
27. No campo Tipo de item, selecione 'Real'.
28. Clique em Adicionar.
29. Clique em Novo para abrir a caixa de diálogo suspensa.
30. No campo Nome, digite 'Id reg. mercadoria'.
    * Id reg de mercadoria  
31. No campo Tipo de item, selecione 'Int64'.
32. Clique em Adicionar.
33. Clique em Novo para abrir a caixa de diálogo suspensa.
34. No campo Nome, digite 'Número do item'.
    * Nº de itens  
35. No campo Tipo de item, selecione 'String'.
36. Clique em Adicionar.
37. Clique em Salvar.
38. Feche a página.

## <a name="modify-model-mapping"></a>Modifique o mapeamento de modelo
1. Na árvore, expanda 'Intrastat (model)'.
2. Na árvore, selecione 'Intrastat (modelo)\Intrastat (mapeamento)'.
    * Modifique o mapeamento de modelo existente para começar a usá-lo para a atualização de dados do aplicativo e para arquivar detalhes de relatório Intrastat.  
3. Clique em Designer.
4. Clique em Novo.
5. No campo Nome, digite 'Atualizar arquivo-morto'.
    * Atualizar arquivo-morto  
6. No campo Direção, selecione 'Para destino'.
7. Clique em Salvar.
    * Este novo mapeamento especifica o fluxo de dados para mover dados (detalhes do relatório Intrastat) do modelo de dados para as tabelas do aplicativo (o destino da atualização). Observe que diferentes itens raiz do modelo devem ser usados para obter os dados do aplicativo para o processo de relatório e depois use os dados do modelo para atualização de dados do aplicativo.   
8. Clique em Designer.
9. Na árvore, selecione 'Modelo de dados\Modelo de dados'.
    * Adicione a fonte de dados obrigatória. Este é o modelo de dados que contém detalhes das transações Intrastat informadas que devem ser preenchidas.  
10. Clique em Adicionar raiz.
11. No campo Nome, digite 'modelo'.
    * modelo  
12. No campo Definição, insira ou selecione o valor "Para atualização de dados do aplicativo".
    * Para atualização de dados do aplicativo  
13. Clique em OK.
14. Na árvore, expanda 'modelo'.
15. Na árvore, selecione 'Funções\Campo calculado'.
16. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto'.
17. Clique em Adicionar.
    * Como você deseja enumerar transações Intrastat informadas para arquivar, a fonte de dados apropriada deverá ser adicionada.  
18. No campo Nome, digite 'Linhas enumeradas'.
    * Linhas enumeradas  
19. Clique em Editar fórmula.
20. Na árvore, selecione 'Lista\ENUMERAR'.
21. Clique em Adicionar função.
22. Na árvore, expanda 'modelo'.
23. Na árvore, expanda 'modelo\Cabeçalho do arquivo morto'.
24. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Arquivar linhas'.
25. Clique em Adicionar fonte de dados.
26. No campo Fórmula, insira “ENUMERAM (modelo."Cabeçalho do arquivo morto.""Arquivar linhas").
    * ENUMERATE(model.'Cabeçalho do arquivo morto'.'Arquivar linhas')  
27. Clique em Salvar.
28. Feche a página.
29. Clique em OK.
30. Clique em Adicionar destino.
    * Adicione as tabelas do aplicativo como destinos obrigatórios que exigem atualizações para arquivar detalhes de transações Intrastat reportadas.  
31. No campo Nome, digite "Arquivar".
    * Arquivar  
32. No campo Nome de tabela, digite “IntrastatArchiveGeneral”.
    * IntrastatArchiveGeneral  
    * Mantenha a ação de registro "Inserir" para poder adicionar registros durante o arquivamento de detalhes de cada processo do relatório Intrastat.  
33. Selecione Sim no campo Log de informações sobre registro.
    * Selecione Sim para obter informações sobre problemas com a atualização de dados do aplicativo.  
34. Selecione Sim no campo Ignorar validação da ação de registro.
    * Selecione Sim para suprimir erros de validação sobre o campo "ID de arquivo morto Intrastat". Isso será feito depois que os registros forem adicionados, com base nas configurações do número de sequência configuradas para a tabela no formulário parâmetros Comércio exterior.  
35. Clique em OK.
    * Associe os elementos da fonte de dados adicional (o modelo filtrado baseado no item raiz selecionado) com elementos de destino adicionado.  
36. Na árvore, expanda 'Arquivar'.
37. Na árvore, expanda 'Arquivar\<Relações'.
38. Na árvore, expanda 'Arquivar\<Relações\IntrastatArchiveDetail'.
39. Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Valor(AmountMST)'.
40. Na árvore, expanda 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas'.
41. Na árvore, expanda 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor'.
42. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Valor'.
43. Clique em Associar.
44. Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Mercadoria(IntrastatCommodity)'.
45. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Id reg. mercadoria'.
46. Clique em Associar.
47. Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Número do item(ItemId)'.
48. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Número do item'.
49. Clique em Associar.
50. Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Número da linha(LineNumber)'.
51. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Número'.
52. Clique em Associar.
53. Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail'.
54. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas'.
55. Clique em Associar.
56. Na árvore, selecione 'Arquivar\Nome do arquivo(FileName)'.
57. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Nome do arquivo'.
58. Clique em Associar.
59. Na árvore, selecione 'Arquivar\Número de linhas(NumberOfLines)'.
60. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Número de linhas'.
61. Clique em Associar.
62. Na árvore, selecione 'Arquivar'.
63. Na árvore, selecione 'modelo\Cabeçalho do arquivo morto'.
64. Clique em Associar.
65. Clique em Salvar.
66. Feche a página.
67. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]