---
title: ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 1 - Criar formato)
description: Este artigo descreve como configurar um formato de relatório eletrônico (ER) para gerar relatórios como arquivos de planilhas (Excel) OPENXML. (Parte 1)
author: kfend
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
ms.openlocfilehash: 3fa8dcac309220d05225e87fd29ef6b741bfcc54
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290414"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 1 - Criar formato)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente. Essas etapas podem ser executadas em qualquer empresa.

Para concluir essas etapas, primeiro você deve concluir essas guias de três tarefas:

"ER Criar um provedor de configuração e marcá-lo como ativo"

"ER Usar dimensões financeiras como uma fonte de dados (Parte 1: Criar modelo de dados)"

"ER Usar dimensões financeiras como uma fonte de dados (Parte 2: Mapeamento de modelo)"

Você também deve baixar e salvar uma cópia local do modelo com um relatório de exemplo encontrado aqui, [Relatório de Serviço Web de Dimensões Financeiras de Exemplo](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx).

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.

## <a name="create-a-new-report-configuration"></a>Criar uma nova configuração de relatório

1. Acesse Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, selecione `Financial dimensions sample model`.
3. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
4. No campo Novo, insira `Format based on data model Financial dimensions sample model`.
    * Use o modelo criado antecipadamente como a fonte de dados de seu novo relatório.  
5. No campo Nome, digite `Sample report with horizontally expandable ranges`.
    * Relatório de exemplo com intervalos expansíveis horizontalmente  
6. No campo Descrição, digite `To make Excel output with dynamically adding columns`.
    * Para fazer saída do Excel com a adição de colunas dinamicamente  
7. No campo Definição de modelo de dados, selecione Entrada.
8. Clique em Criar configuração.

## <a name="design-the-report-format"></a>Criar o formato do relatório

1. Clique em Designer.
2. Ative o botão de alternância `Show details`.
3. No Painel de Ação, clique em Importar.
4. Clique em Importar do Excel.
5. Clique em Anexos.
    * Importe o modelo do relatório. Use o arquivo Excel que você baixou para isso.  
6. Clique em Novo.
7. Clique em Arquivo.
8. Feche a página.
9. No campo Modelo, insira ou selecione um valor.
    * Selecione o modelo baixado.  
10. Clique em OK.
    * Adicione um novo intervalo para criar dinamicamente saídas do Excel com quantas colunas você selecionar (no formulário da caixa de diálogo do usuário) para as dimensões financeiras. Cada célula para cada coluna representará o nome de uma única dimensão financeira.  
11. Clique em Adicionar para abrir a caixa de diálogo suspensa.
12. Na árvore, selecione `Excel\Range`.
13. No campo Intervalo do Excel, digite `DimNames`.
    * DimNames  
14. No campo Direção de replicações, selecione `Horizontal`.
15. Clique em OK.
16. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
17. Clique em Mover para cima.
18. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Cell<DimNames>`.
19. Clique em Recortar.
20. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
21. Clique em Colar.
22. Na árvore, expanda `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
23. Na árvore, expanda `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
24. Na árvore, expanda `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
25. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
    * Adicione um novo intervalo para criar dinamicamente saídas do Excel com quantas colunas você selecionar (no formulário da caixa de diálogo do usuário) para as dimensões financeiras. Cada célula para cada coluna representará o valor de uma única dimensão financeira para cada transação do relatório.  
26. Clique em Adicionar intervalo.
27. No campo Intervalo do Excel, digite `DimValues`.
    * DimValues  
28. No campo Direção de replicações, selecione `Horizontal`.
29. Clique em OK.
30. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>`.
31. Clique em Recortar.
32. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
33. Clique em Colar.
34. Na árvore, expanda `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.

## <a name="map-format-elements-to-data-sources"></a>Mapear elementos de formato para as fontes de dados

1. Clique na aba Mapeamento.
2. Na árvore, expanda `model: Data model Financial dimensions sample model`.
3. Na árvore, expanda `model: Data model Financial dimensions sample model\Journal: Record list`.
4. Na árvore, expanda `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
5. Na árvore, expanda `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
6. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>`.
7. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String`.
8. Clique em Associar.
9. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
10. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
11. Clique em Associar.
12. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>`.
13. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real`.
14. Clique em Associar.
15. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>`.
16. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real`.
17. Clique em Associar.
18. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>`.
19. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String`.
20. Clique em Associar.
21. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>`.
22. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date`.
23. Clique em Associar.
24. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>`.
25. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String`.
26. Clique em Associar.
27. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>`.
28. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
29. Clique em Associar.
30. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
31. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
32. Clique em Associar.
33. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>`.
34. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
35. Clique em Associar.
36. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
37. Na árvore, selecione `model: Data model Financial dimensions sample model\Journal: Record list`.
38. Clique em Associar.
39. Na árvore, expanda `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
40. Na árvore, selecione `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String`.
41. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>`.
42. Clique em Associar.
43. Na árvore, selecione `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
44. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
45. Clique em Associar.
46. Na árvore, selecione `Excel = "SampleFinDimWsReport"\Cell<CompanyName>`.
47. Na árvore, selecione `model: Data model Financial dimensions sample model\Company: String`.
48. Clique em Associar.
49. Clique em Salvar.
50. Feche a página.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
