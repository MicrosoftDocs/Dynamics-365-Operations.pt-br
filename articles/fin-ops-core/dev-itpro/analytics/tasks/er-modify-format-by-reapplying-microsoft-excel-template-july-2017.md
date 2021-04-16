---
title: Modificar formatos ao reaplicar modelos do Excel
description: Para completar as etapas deste procedimento, primeiro você deve concluir o procedimento ER - Criar uma configuração para gerar relatórios no formato OPENXML.
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
ms.openlocfilehash: 24eb64679b458d14e30dc5b4365c7305d71cfc4c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754881"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a>Modificar formatos ao reaplicar modelos do Excel

[!include [banner](../../includes/banner.md)]

Para completar as etapas deste procedimento, primeiro você deve concluir o procedimento ER - Criar uma configuração para gerar relatórios no formato OPENXML.

Este procedimento explica como modificar uma configuração de formato de relatório eletrônico (ER) reaplicando um modelo modificado do Microsoft Excel. Nesse procedimento, você importará um modelo do Excel modificado para configurações de formato de ER que foi criado para a empresa exemplo, Litware, Inc., e depois gerará documentos eletrônicos. Esse procedimento é destinado a usuários com a função de administrador do sistema ou desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de GBSI. Antes de começar, faça download e salve o arquivo SampleVendPaymWsReport2.xlsx que é listado no tópico de Ajuda. Modifique o formato de relatório eletrônico reaplicando um modelo do Excel (modify-electronic-reporting-format-reapply-excel-template/).

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar este provedor de configuração, conclua as etapas no procedimento Criar um provedor de configuração e marcá-lo como ativo.  

## <a name="select-the-er-format"></a>Selecione o formato de ER
1. Clique em Configurações de relatórios.
2. Na árvore, expanda 'Modelo de pagamento'.
3. Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".
4. Clique em Anexos.
    * Observe que o arquivo de Excel SampleVendPaymWsReport.xlsx atualmente é usado como modelo para o processamento do diário de pagamento.   
5. Clique em Abrir.
    * Clique em Abrir para explorar o layout do modelo do Excel.  
    * Revise o modelo. Observe que atualmente ele inclui os seguintes detalhes de cada linha de pagamento: número de conta de fornecedor, nome do fornecedor, banco, número de roteiro, número da conta, débito, crédito e moeda. Para este exemplo, queremos estender esta lista, adicionando detalhes sobre a data de pagamento.   
6. Feche a página.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Reaplique um novo modelo de Excel para o formato de ER
1. Clique em Designer.
    * Abre a versão de rascunho de formato de ER selecionado para edição.  
2. No Painel de Ação, clique em Importar.
3. Clique em Atualizar do Excel.
    * Clique em "Atualizar modelo" e, em seguida, selecione o arquivo, SampleVendPaymWsReport2.xlsx.  
    * Clique em Atualizar modelo e procure o arquivo SampleVendPaymWsReport2.xlsx baixado anteriormente.  
4. Clique em OK.
    * O modelo SampleVendPaymWsReport2.xlsx é aplicado. A estrutura de formato de ER é sincronizada com o conteúdo do modelo, cujos elementos são adicionados ao formato de ER. Todos os elementos existentes no formato de ER que não estão incluídos no modelo são removidos da definição de formato.  
5. Na árvore, selecione 'Excel'.
    * Observe que o campo Modelo agora contém uma referência para o novo modelo.   
6. Clique em Anexos.
7. Clique em Abrir.
    * Clique em Abrir para explorar o layout do modelo do Excel modificado.  
    * Revise o modelo. Observe que agora ele contém uma linha para a data de pagamento.   
8. Feche a página.
9. Na árvore, expanda 'Excel'.
10. Na árvore, expanda "Excel\PaymLines".
11. Na árvore, selecione 'Excel\PaymLines\PaymDate'.
    * Observe que o formato de ER agora contém mais um item. Uma célula, PaymDate, foi adicionada ao modelo do Excel.  
12. Clique na aba Mapeamento.
13. Na árvore, expanda 'modelo'.
14. Na árvore, expanda 'modelo\Pagamentos'.
15. Na árvore, selecione 'modelo\Pagamentos\Data da transação(DataTransação)'.
16. Clique em Associar.
    * Especifique os dados que são adicionados à nova célula no tempo de execução.  
17. Clique em Salvar.
18. Feche a página.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Habilite a versão de rascunho alterada do formato de ER para usar no processamento do diário de pagamento
1. No Painel de Ação, clique em Configurações.
2. Clique em Parâmetros de usuário.
3. Selecione Sim no campo Executar configurações.
4. Clique em OK.
5. Clique em Editar.
6. Selecione Sim no campo Executar Rascunho.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Use a versão de rascunho alterada do formato de ER para processamento do diário de pagamento

Revise a planilha criada, incluindo novos detalhes de linhas de pagamento – data de pagamento.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]