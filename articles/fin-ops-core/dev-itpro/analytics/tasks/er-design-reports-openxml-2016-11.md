---
title: ER Projetar uma configuração para gerar relatórios no formato OPENXML (Novembro de 2016)
description: Este tópico descreve como criar uma nova configuração de relatório eletrônico (ER) que contém um modelo para gerar documentos de pagamento eletrônico no formato OPENXML.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b832961061d05e3f1ae046f820bc7a37baaf90c
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092657"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Projetar uma configuração para gerar relatórios no formato OPENXML (Novembro de 2016)

[!include [banner](../../includes/banner.md)]

Este tópico explica como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML. Essa configuração será usada para processar pagamentos do fornecedor.

Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas na empresa GBSI.

Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo". Você também deve ter um arquivo Excel que é importado ao criar o modelo. Esse arquivo pode ser acessado de [Modelo de relatório de pagamento](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Carregar a configuração do modelo de dados de pagamentos
1. No Painel de Navegação, vá para **Módulos > Administração da organização > Espaços de trabalho > Relatório eletrônico**.
2. Na lista, marque o provedor de configuração para a empresa de exemplo, "Litware, Inc." Se você não visualizar o provedor de configuração, você deve primeiro concluir as etapas em [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).
3. Selecione **Definir como ativo**.
4. Selecione **Repositórios**. Selecione um repositório para o tipo Recursos de operações, se disponível. Se estiver disponível, pule as etapas a seguir sobre criar um novo repositório.  
5. Selecione **Adicionar** para abrir a caixa de diálogo suspensa.
6. No campo **Tipo de repositório de configuração**, insira `Operations resourcesdd`.
7. Selecione **Criar repositório**.
8. Selecione **OK**.
9. Selecione **Abrir**.
10. Na árvore, selecione **Modelo de pagamento**.
11. Selecione **Importar**. Importar este modelo de dados. Será usado como a fonte de dados em uma nova configuração de formato. Ignorar essa etapa se essa configuração já tiver sido importada.  
12. Selecione **Sim**.
13. Feche as páginas até retornar à página de relatórios eletrônicos.

## <a name="create-a-new-format-configuration"></a>Criar uma nova configuração de formato
1. Selecione **Configurações de relatórios**.
2. Na árvore, selecione **Modelo de pagamento**.
3. Selecione **Criar configuração** para abrir a caixa de diálogo suspensa.
4. No campo **Novo**, insira `Format based on data model PaymentModel`. Criar um formato com base no modelo de dados do PaymentModel.
5. No campo **Nome**, digite `Sample worksheet report`. Relatório da planilha de exemplo  
6. No campo **Descrição**, digite `Sample worksheet report for vendors' payments`. Relatório de planilha de amostra para pagamentos do fornecedor.  
7. No campo **Definição do modelo de dados**, insira ou selecione um valor. Selecione a definição **CustomerCreditTransferInitiation**.  
8. Selecione **Criar configuração**.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Criar um novo documento no formato da folha OPENXML
1. Na árvore, selecione **Modelo de pagamento\Relatório de planilha de amostra**.
2. Selecione **Designer**.
3. No Painel de Ações, selecione **Importar**.
4. Selecione **Importar do Excel**.
5. Selecione **Anexos**. Anexar o documento existente do Excel como um modelo.  
6. Selecione **Novo**.
7. Selecione **Arquivo**. Apontar para o arquivo existente do Excel.  
8. Feche a página.
9. No campo **Modelo**, insira ou selecione um valor. Selecione o arquivo Excel anexado a ser usado como um modelo.  
10. Selecione **OK**. Observe que os componentes do formato ER foram criados no formato criador com base na estrutura do documento de referência do MS Excel (intervalos nomeados).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Criar uma nova fonte de dados para calcular totais por código de moeda
1. Selecione a guia **Mapeamento**.
2. Selecione **Adicionar raiz** para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione **Funções\Agrupar por**.
4. No campo **Nome**, digite `PaymentByCurrency`.
5. Selecione **Editar grupo por**.
6. Na árvore, expanda **modelo**, selecione **modelo\Pagamentos**.
7. Selecione **Adicionar campo a**.
8. Selecione **O que agrupar**.
9. Na árvore, expanda **modelo\Pagamentos** e selecione **modelo\Pagamentos\Moeda**.
10. Selecione **Adicionar campo a**.
11. Selecione **Campos agrupados**.
12. Na árvore, selecione **modelo\Pagamentos\Valor instruído(ValorInstruído)**.
13. Selecione **Adicionar campo a** e **Campos de agregação**.
14. No campo **Método**, selecione uma opção. Selecione a função **agregada de SUM**.  
15. No campo **Nome**, digite `TotalInstructuredAmount`.
16. Selecione **Salvar**.
17. Feche a página.
18. Selecione **OK**.

## <a name="map-format-components-to-data-sources"></a>Componentes de formato de mapa para fontes de dados
1. Na árvore, selecione **modelo\Pagamentos\Participante Iniciante(InitiatingParty)\Nome** e **Excel\ReportHeader\CompanyName**.
2. Selecione **Associar**.
3. Na árvore, selecione **modelo\Pagamentos\Credor\Identificação\ID da fonte(SourceID)** e **Excel\PaymLines\VendAccountName**.
4. Selecione **Associar**.
5. Na árvore, selecione **modelo\Pagamentos\Credor\Nome** e **Excel\PaymLines\VendName**.
6. Selecione **Associar**.
7. Na árvore, selecione **modelo\Pagamentos\Agente do Credor(CreditorAgent)\Nome** e **Excel\PaymLines\Banco**.
8. Selecione **Associar**.
9. Na árvore, selecione **modelo\Pagamentos\Agente credor(CreditorAgent)\Número de roteiro(RoutingNumber)** e **Excel\PaymLines\RoutingNumber**.
10. Selecione **Associar**.
11. Na árvore, selecione **modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação\Número** e **Excel\PaymLines\AccountNumber**.
12. Selecione **Associar**.
13. Na árvore, selecione **modelo\Pagamentos\Valor instruído(ValorInstruído)** e **Excel\PaymLines\Débito**.
14. Selecione **Associar**.
15. Na árvore, selecione **modelo\Pagamentos\Moeda** e **Excel\PaymLines\Moeda**.
16. Selecione **Associar**.
17. Na árvore, selecione **PaymentByCurrency\agrupado\Moeda** e **Excel\SummaryLines\SummaryCurrency**.
18. Selecione **Associar**.
19. Na árvore, selecione **PaymentByCurrency\agregado\TotalInstructuredAmount** e **Excel\SummaryLines\SummaryAmount**.
20. Selecione **Associar**.
21. Na árvore, selecione **PaymentByCurrency** e **Excel\SummaryLines**.
22. Selecione **Associar**.
23. Na árvore, selecione **modelo\Pagamentos** e **Excel\PaymLines**.
24. Selecione **Associar**.
25. Selecione **Salvar** e feche a página.

## <a name="use-the-created-configuration-for-payments-processing"></a>Usar a configuração criada para processamento de pagamentos
1. Selecione **Alterar status**.
2. Selecione **Concluir**.
3. Selecione **OK**.
4. No Painel de Navegação, vá para **Módulos > Contas a pagar > Configuração de pagamento > Formas de pagamento**.
5. Use o Filtro Rápido para filtrar o campo **Forma de pagamento** com o valor **Eletrônico**.
6. Selecione **Editar**.
7. Expanda a seção **Formatos de arquivo**.
8. Selecione **Sim** no campo **Relatórios eletrônicos genéricos**.
9. No campo **Exportar configuração de formato**, insira ou selecione um valor. Selecione a configuração **Relatório de planilha de amostra**.  
10. Selecione **Salvar**.
11. Feche a página.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Use a configuração criada para testar de processar diários de pagamentos
1. No Painel de Navegação, vá para **Módulos > Contas a pagar > Pagamentos > Diário de pagamentos**.
2. Selecione **Novo** para criar um novo diário de pagamentos.
3. No campo **Nome**, digite **VendPay**.
4. Selecione **Linhas**.
5. No campo **Conta**, especifique os valores `GB_SI_000001`.
6. Defina **Débito** como `1000`.
7. Selecione **Novo**.
8. No campo **Conta**, especifique os valores `GB_SI_000005`.
9. Defina **Débito** como `2000`.
10. No campo **Moeda**, digite `EUR`.
11. No campo **Contrapartida**, especifique os valores `GBSI OPER`.
12. No campo **Método de pagamento**, digite `Electronic`.
13. Selecione **Salvar**.
14. Selecione **Gerar pagamentos**.
15. No campo **Método de pagamento**, digite `Electronic`.
16. No campo **Nome de arquivo**, digite `Payments`.
17. No campo **Conta bancária**, digite `GBSI OPER`.
18. Selecione **OK** e **OK** novamente. Revise a planilha criada, incluindo detalhes de linhas de pagamento além do total para cada código de moeda usado na mensagem de pagamento.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]