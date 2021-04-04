---
title: Modificar formatos para gerar documentos com dados de aplicativo
description: Este tópico descreve como criar configurações de relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo.
author: NickSelin
manager: AnnBe
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
ms.openlocfilehash: ad75adb22efbd90d3fb4a71a2d592950a66bafd8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565432"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Modificar formatos para gerar documentos com dados de aplicativo

[!include [banner](../../includes/banner.md)]

Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 3: Modificar modelo e mapeamento)".

As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo. Nesse procedimento, você modificará as configurações de ER não apenas para usá-las para gerar documentos eletrônicos, mas também para atualizar dados do aplicativo. Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.


## <a name="modify-format-to-collect-details-of-reporting"></a>Modificar o formato para obter detalhes de relatório
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Intrastat (model)'.
3. Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.
4. Clique em Designer.
5. Na árvore, expanda 'Arquivo'.
6. Na árvore, expanda 'Arquivo\Declaração'.
7. Na árvore, selecione 'Arquivo\Declaração\Dados'.
8. No campo Multiplicidade, selecione 'Um muitos'.
    * Configure esse elemento de formato para arquivar detalhes do processo de relatório Intrastat. Esse item representa o registro de cabeçalho de arquivo morto.  
9. Na árvore, expanda 'Arquivo\Declaração\Dados'.
10. Na árvore, selecione 'Arquivo\Declaração\Dados\Item'.
11. No campo Multiplicidade, selecione 'Zero muitos'.
    * Configure esse elemento de formato para arquivar detalhes do processo de relatório Intrastat. Esse item representará a lista de linhas arquivadas.  
12. Na árvore, expanda 'Arquivo\Declaração\Dados\Item'.
13. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim1'.
14. Selecione Sim no campo Excluído.
    * Você não arquivará esses dados, dessa forma você poderá excluir esse elemento de formato dos dados de origem dos detalhes de relatório Intrastat.  
15. Na árvore, expanda 'Arquivo\Declaração\Dados\Item\Dim1'.
16. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim1\propriedade'.
17. Selecione Sim no campo Excluído.
18. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim1\data'.
19. Selecione Sim no campo Excluído.
20. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim2'.
21. Selecione Sim no campo Excluído.
22. Na árvore, expanda 'Arquivo\Declaração\Dados\Item\Dim2'.
23. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim2\propriedade'.
24. Selecione Sim no campo Excluído.
25. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim2\código'.
26. Selecione Sim no campo Excluído.
27. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim3'.
    * Vários elementos de formato podem ter o mesmo nome. Por exemplo, Dim. Você não pode reconhecê-los explicitamente quando usar este formato como uma fonte de dados para arquivar detalhes de relatório Intrastat, dessa forma você precisa definir os nomes alternativos para esses elementos de formato.   
28. No campo Nome, digite 'Valor'.
    * Valor  
29. No campo Multiplicidade, selecione 'Exatamente um'.
30. Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim4'.
31. No campo Nome, digite 'Item'.
    * Item  
32. No campo Multiplicidade, selecione 'Exatamente um'.
    * Além dos elementos de formato de design, os detalhes do relatório Intrastat devem ser arquivados: identificação de registro exclusivo de cada item de mercadorias relatado e nome de arquivo gerado. Como os dados não serão preenchidos no relatório Intrastat, você precisará adicionar o formato relacionado a esses elementos de detalhe como itens de fonte de dados.  
33. Na árvore, selecione 'Arquivo\Declaração\Dados'.
34. Clique em Adicionar para abrir a caixa de diálogo suspensa.
35. Na árvore, selecione 'Origem de dados\Item'.
36. No campo Nome, digite 'Nome do arquivo'.
    * Nome do arquivo  
37. No campo Tipo de dados, selecione 'String'.
38. Clique em OK.
39. Na árvore, selecione 'Arquivo\Declaração\Dados\Item'.
40. Clique em Adicionar Item.
41. No campo Nome, digite "ID reg. mercadoria".
    * ID reg de mercadoria  
42. No campo Tipo de dados, selecione 'Int64'.
43. Clique em OK.
44. Clique na aba Mapeamento.
45. Na árvore, selecione 'Arquivo\Declaração\Dados\Nome do arquivo'.
46. Clique em Associar.
47. Na árvore, expanda 'modelo'.
48. Na árvore, expanda 'modelo\Transações'.
49. Na árvore, selecione "Arquivo\Declaração\Dados\Item = model.Transactions\ID reg. mercadoria".
50. Na árvore, selecione "modelo\Transações\ID reg. mercadoria".
51. Clique em Associar.
52. Clique em Salvar.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Modificar o formato para memorizar detalhes de relatório

1. Clique em Mapear formato para modelo.
2. Clique em Novo.
3. No campo Definição, insira ou selecione o item raiz "Para atualização de dados do aplicativo".
    * Para atualização de dados do aplicativo.
4. No campo Nome, digite "Mapeamento de dados de atualização".
    * Mapeamento para atualizar dados  
5. Clique em Salvar.
    * Este mapeamento define como os detalhes do relatório Intrastat são reunidos no modelo de dados, a estrutura especificada pelo item raiz selecionado "Para atualização de dados do aplicativo". Esses detalhes, o mapeamento de modelo com o mesmo item raiz "Para atualização de dados do aplicativo", e a direção e "Para destino" serão usados para a atualização de dados do aplicativo. A atualização de dados do aplicativo é iniciada imediatamente após o relatório Intrastat de saída ser gerado. A atualização de dados do aplicativo pode ser ignorada no tempo de execução, mas o modelo de dados deve estar vazio (contendo a lista de registros vazia).
6. Clique em Designer.
    * O formato de relatório Intrastat de saída será adicionada, por padrão, como uma origem de dados para este mapeamento de modelo.  
    * Associe os elementos do relatório criado (apresentado como a fonte de dados) aos elementos do modelo de dados, que é filtrado com base no item raiz do modelo selecionado.  
7. Na árvore, expanda 'Archive header'.
8. Na árvore, expanda 'Cabeçalho do arquivo morto\Arquivar linhas'.
9. Na árvore, expanda 'format'.
10. Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)'.
11. Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..* (Dados)'.
12. Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..* (Dados)\Item: Elemento XML 0..* (Item)'.
13. Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..* (Dados)\Item: Elemento XML 0..* (Item)\Dim3: Elemento XML 1..1 (Valor)'.
14. Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..* (Dados)\Item: Elemento XML 0..*(Item)\Dim4: Elemento XML 1..1 (Item)'.
15. Na árvore, selecione 'Cabeçalho do arquivo morto\Número de linhas'.
16. Clique em Editar.
17. Na árvore, selecione 'Lista\CONTAGEM'.
18. Clique em Adicionar função.
19. Na árvore, expanda 'format'.
20. Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)'.
21. Na árvore, expanda `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
22. Na árvore, selecione `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
23. Clique em Adicionar fonte de dados.
24. No campo Fórmula, insira 'COUNT(format.Declaration.Data.Item)'.
    * CONTAGEM (formato.Declaração.Dados.Item)  
25. Clique em Salvar.
26. Feche a página.
27. Na árvore, selecione 'Cabeçalho do arquivo morto\Nome do arquivo'.
28. Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..* (Dados)\Nome do arquivo: Cadeia de caracteres do item (Nome do arquivo)'.
29. Clique em Associar.
30. Na árvore, selecione `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)`.
31. Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas\Número do Item'.
32. Clique em Associar.
33. Na árvore, selecione `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)`.
34. Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas\Valor'.
35. Clique em Associar.
36. Na árvore, selecione `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec ID: Item Int64(Commodity rec ID)`.
37. Na árvore, selecione "Cabeçalho do arquivo morto\Arquivar linhas\ID reg. mercadoria".
38. Clique em Associar.
39. Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas'.
40. Na árvore, selecione `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
41. Clique em Associar.
42. Na árvore, selecione 'Cabeçalho do arquivo-morto'.
43. Na árvore, selecione `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
44. Clique em Associar.
45. Clique em Salvar.
46. Feche a página.
47. Feche a página.
48. Feche a página.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]