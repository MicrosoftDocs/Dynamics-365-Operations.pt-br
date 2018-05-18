--- 
title: "Criar uma configuração para gerar relatórios no formato OpenXML para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML."
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
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 09789957839097ba2898544102af908c198090c7
ms.contentlocale: pt-br
ms.lasthandoff: 11/14/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a>Criar uma configuração para gerar relatórios no formato OpenXML para relatório eletrônico (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML. Essa configuração será usada para processar pagamentos do fornecedor.



Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas na empresa GBSI.



Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“. Você também deve baixar e salvar o arquivo do Microsoft Excel, [Modelo de relatório de pagamento](https://go.microsoft.com/fwlink/?linkid=862266). 

## <a name="upload-the-payments-data-model-configuration"></a>Carregar a configuração do modelo de dados de pagamentos
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Na lista, marque a linha selecionada.
    * Selecione o provedor de configuração para a empresa de exemplo, 'Litware, Inc.' Se você não visualizar o provedor de configuração, você deve primeiro concluir as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.  
3. Clique em Definir como ativo.
4. Clique em Repositórios.
    * Selecione um repositório para o tipo Recursos de operações, se disponível. Se estiver disponível, pule as etapas a seguir sobre criar um novo repositório.  
5. Clique em Adicionar para abrir a caixa de diálogo suspensa.
6. No campo Tipo de repositório de configuração, insira 'Recursos de operações'.
7. Clique em Criar repositório.
8. Clique em OK.
9. Clique em Abrir.
10. Na árvore, selecione 'Modelo de pagamento'.
11. Clique em Importar.
    * Importar este modelo de dados. Será usado como a fonte de dados em uma nova configuração de formato. Ignorar essa etapa se essa configuração já tiver sido importada.  
12. Clique em Sim.
13. Feche a página.
14. Feche a página.

## <a name="create-a-new-format-configuration"></a>Criar uma nova configuração de formato
1. Clique em Configurações de relatórios.
2. Na árvore, selecione 'Modelo de pagamento'.
3. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
4. No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.
    * Criar um formato com base no modelo de dados do PaymentModel.  
5. No campo Nome, digite "Relatório de planilha de exemplo".
    * Relatório da planilha de exemplo  
6. No campo Tipo de descrição, digite "Relatório de planilha de amostra para pagamentos de fornecedor".
    * Relatório de planilha de amostra para pagamentos do fornecedor.  
7. No campo Definição do modelo de dados, insira ou selecione um valor.
    * Selecione a definição "CustomerCreditTransferInitiation".  
8. Clique em Criar configuração.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Criar um novo documento no formato da folha OPENXML
1. Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".
2. Clique em Designer.
3. No Painel de Ação, clique em Importar.
4. Clique em Importar do Excel.
5. Clique em Anexos.
    * Anexar o documento existente do Excel como um modelo.  
6. Clique em Novo.
7. Clique em Arquivo.
    * Apontar para o arquivo existente do Excel.  
8. Feche a página.
9. No campo Modelo, insira ou selecione um valor.
    * Selecione o arquivo Excel anexado a ser usado como um modelo.  
10. Clique em OK.
    * Observe que os componentes do formato ER foram criados no formato criador com base na estrutura do documento de referência do MS Excel (intervalos nomeados).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Criar uma nova fonte de dados para calcular totais por código de moeda
1. Clique na aba Mapeamento.
2. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione 'Funções\Agrupar por'.
4. No campo Nome, digite 'PaymentByCurrency'.
    * PaymentByCurrency  
5. Clique em Editar grupo por.
6. Na árvore, expanda 'modelo'.
7. Na árvore, selecione 'modelo\Pagamentos'.
8. Clique em Adicionar campo a.
9. Clique em O que agrupar.
10. Na árvore, expanda 'modelo\Pagamentos'.
11. Na árvore, selecione 'modelo\Pagamentos\Moeda'.
12. Clique em Adicionar campo a.
13. Clique em Campos agrupados.
14. Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.
15. Clique em Adicionar campo a.
16. Clique em Campos de agregação.
17. No campo Método, selecione uma opção.
    * Selecione a função agregada de SUM.  
18. No campo Nome, digite 'TotalInstructuredAmount'.
    * TotalInstructuredAmount  
19. Clique em Salvar.
20. Feche a página.
21. Clique em OK.

## <a name="map-format-components-to-data-sources"></a>Componentes de formato de mapa para fontes de dados
1. Na árvore, expanda 'modelo'.
2. Na árvore, expanda 'modelo\Pagamentos'.
3. Na árvore, expanda "modelo\Pagamentos\Participante Iniciante(InitiatingParty)".
4. Na árvore, selecione "modelo\Pagamentos\Participante Iniciante(InitiatingParty)\Nome".
5. Na árvore, expanda "Excel\ReportHeader".
6. Na árvore, selecione "Excel\ReportHeader\CompanyName".
7. Clique em Associar.
8. Na árvore, expanda 'modelo\Pagamentos\Credor'.
9. Na árvore, expanda 'modelo\Pagamentos\Credor\Identificação'.
10. Na árvore, selecione 'modelo\Pagamentos\Credor\Identificação\ID da fonte(SourceID)'.
11. Na árvore, expanda "Excel\PaymLines".
12. Na árvore, selecione "Excel\PaymLines\VendAccountName".
13. Clique em Associar.
14. Na árvore, selecione 'modelo\Pagamentos\Credor\Nome'.
15. Na árvore, selecione "Excel\PaymLines\VendName".
16. Clique em Associar.
17. Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.
18. Na árvore, selecione 'modelo\Pagamentos\Agente do Credor(CreditorAgent)\Nome'.
19. Na árvore, selecione "Excel\PaymLines\Banco".
20. Clique em Associar.
21. Na árvore, selecione 'modelo\Pagamentos\Agente credor(CreditorAgent)\Número de roteiro(RoutingNumber)'.
22. Na árvore, selecione "Excel\PaymLines\RoutingNumber".
23. Clique em Associar.
24. Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.
25. Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação'.
26. Na árvore, selecione 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação\Número'.
27. Na árvore, selecione "Excel\PaymLines\AccountNumber".
28. Clique em Associar.
29. Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.
30. Na árvore, selecione "Excel\PaymLines\Débito".
31. Clique em Associar.
32. Na árvore, expanda 'modelo\Pagamentos\Credor'.
33. Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.
34. Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.
35. Na árvore, selecione 'modelo\Pagamentos\Moeda'.
36. Na árvore, selecione "Excel\PaymLines\Moeda".
37. Clique em Associar.
38. Na árvore, expanda 'PaymentByCurrency'.
39. Na árvore, expanda 'PaymentByCurrency\agrupado'.
40. Na árvore, selecione 'PaymentByCurrency\agrupado\Moeda'.
41. Na árvore, expanda "Excel\SummaryLines".
42. Na árvore, selecione "Excel\SummaryLines\SummaryCurrency".
43. Clique em Associar.
44. Na árvore, expanda "PaymentByCurrency\agregado".
45. Na árvore, selecione 'PaymentByCurrency\agregado\TotalInstructuredAmount'.
46. Na árvore, selecione "Excel\SummaryLines\SummaryAmount".
47. Clique em Associar.
48. Na árvore, selecione 'PaymentByCurrency'.
49. Na árvore, selecione "Excel\SummaryLines".
50. Clique em Associar.
51. Na árvore, selecione 'modelo\Pagamentos'.
52. Na árvore, selecione "Excel\PaymLines".
53. Clique em Associar.
54. Clique em Salvar.
55. Feche a página.

## <a name="use-the-created-configuration-for-payments-processing"></a>Usar a configuração criada para processamento de pagamentos
1. Clique em Alterar status.
2. Clique em Concluir.
3. Clique em OK.
4. Feche a página.
5. Feche a página.
6. Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.
7. Use o Filtro Rápido para filtrar o campo Method of payment com o valor "Eletrônico".
    * Eletrônico  
8. Clique em Editar.
9. Expanda a seção Formatos de arquivo.
10. Selecione Sim no campo eletrônico Genérico do relatório.
11. No campo Exportar configuração de formato, insira ou selecione um valor.
    * Selecione a configuração "Relatório de planilha de amostra".  
12. Clique em Salvar.
13. Feche a página.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Use a configuração criada para testar de processar diários de pagamentos
1. Vá para Contas a pagar > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
    * Crie um novo diário de pagamento.  
3. No campo Nome, digite 'VendPay'.
    * VendPay  
4. Clique em Linhas.
5. No campo Conta, especifique os valores 'GB_SI_000001'.
    * GB_SI_000001  
6. Definir Débito como '1000'.
7. Clique em Novo.
8. No campo Conta, especifique os valores 'GB_SI_000005'.
    * GB_SI_000005  
9. Definir Débito como '2000'.
10. No campo Moeda, digite 'EUR'.
    * EUR  
11. No campo Contrapartida, especifique os valores 'GBSI OPER'.
    * GBSI OPER  
12. No campo Método de pagamento, digite "Eletrônico".
    * Eletrônico  
13. Clique em Salvar.
14. Clique em Gerar pagamentos.
15. No campo Método de pagamento, digite "Eletrônico".
    * Eletrônico  
16. No campo Nome do arquivo, digite "Pagamentos".
    * Por exemplo, digite Pagamentos.  
17. No campo Conta bancária, digite 'GBSI OPER'.
    * GBSI OPER  
18. Clique em OK.
19. Clique em OK.
    * Revise a planilha criada, incluindo detalhes de linhas de pagamento além do total para cada código de moeda usado na mensagem de pagamento.  


