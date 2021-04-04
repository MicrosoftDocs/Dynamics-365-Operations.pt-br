---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 2 - Estender modelo de dados)
description: Este tópico descreve como configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída de ER. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b47c35790ce04a494b6c58f6e04fa9b829d2ab93
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559764"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 2 - Estender modelo de dados)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER. Essas etapas podem ser executadas em qualquer empresa.

Para concluir estas etapas, primeiramente você deve concluir as etapas no guia de tarefas "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 1: preparar modelo de dados)".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Estender o modelo de dados para apresentar os arquivos de gerenciamento de documentos nele
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, expanda 'Modelo de fatura de cliente'.
4. Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.
5. Clique em Designer.
6. Na árvore, selecione 'Fatura de cliente(InvoiceCustomer)'.
    * Estenderemos este modelo de dados para expor nele todos os arquivos associados a uma ordem de venda que esteja relacionada a um processamento eletrônico de fatura.  
7. Clique em Novo para abrir a caixa de diálogo suspensa.
8. No campo Nome, digite 'Anexos da fatura'.
    * Anexos da fatura  
9. No campo Tipo de item, selecione 'Lista de Registro'.
10. Clique em Adicionar.
11. Clique em Novo para abrir a caixa de diálogo suspensa.
12. No campo Nome, digite 'Conteúdo do arquivo'.
    * Conteúdo do arquivo  
13. No campo Tipo de item, selecione 'Contêiner'.
14. Clique em Adicionar.
15. Clique em Novo para abrir a caixa de diálogo suspensa.
16. No campo Nome, digite 'Nome do arquivo'.
    * Nome do arquivo  
17. No campo Tipo de item, selecione 'String'.
18. Clique em Adicionar.

## <a name="map-new-data-model-elements-to-data-sources"></a>Mapear novos elementos do modelo de dados para fontes de dados
1. Clique em Mapear modelo para fonte de dados.
2. Use o Filtro Rápido para filtrar no campo Definição com um valor de 'InvoiceCustomer'.
    * InvoiceCustomer  
    * Mapearemos novos elementos do modelo para utilizar fontes de dados apropriadas.  
3. Clique em Designer.
4. Na árvore, selecione 'Anexos da fatura'.
5. Na árvore, expanda 'Anexos da fatura'.
6. Na árvore, selecione 'Anexos da fatura\Nome do arquivo'.
7. Clique em Editar.
8. No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. Clique em Salvar.
10. Feche a página.
11. Na árvore, selecione 'Anexos da fatura\Conteúdo do arquivo'.
12. Clique em Editar.
13. No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. Clique em Salvar.
15. Feche a página.
16. Na árvore, selecione 'Anexos da fatura'.
17. Clique em Editar.
18. No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. Clique em Salvar.
20. Feche a página.
21. Clique em Salvar.
22. Feche a página.
23. Feche a página.
24. Feche a página.
25. Clique em Alterar status.
26. Clique em Concluir.
27. Clique em OK.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]