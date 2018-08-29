--- 
title: "Criar formatos para usar arquivos de gerenciamento de documentos em saídas de ER"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: 934775bbdda13238e16fba91dcb90d6d3249e812
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-formats-to-use-document-management-files-in-er-output"></a>Criar formatos para usar arquivos de gerenciamento de documentos em saídas de ER

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER. Essas etapas podem ser executadas em qualquer empresa.

Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 2: estender modelo de dados)".

Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="create-a-format-to-process-invoices"></a>Criar um formato para processar faturas
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, expanda 'Modelo de fatura de cliente'.
4. Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.
    * Você criará um formato para gerar mensagens eletrônicas com informações sobre todos os arquivos que foram anexados a uma ordem de venda que esteja relacionada a um processamento eletrônico de fatura.  
5. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
6. No campo Novo, insira 'Formato baseado no modelo de dados Modelo de fatura de cliente (personalizada)'.
7. No campo Nome, digite 'Mensagem de exemplo da fatura eletrônica'.
    * Mensagem de exemplo da fatura eletrônica  
8. No campo Definição do modelo de dados, insira ou selecione um valor.
    * InvoiceCustomer  
9. Clique em Criar configuração.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Criar um formato para popular anexos para a geração de uma mensagem no formato MIME
1. Clique em Designer.
2. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione 'XML\Elemento'.
4. No campo Nome, digite 'Fatura'.
    * Fatura  
5. Clique em OK.
6. Clique em Adicionar para abrir a caixa de diálogo suspensa.
7. Na árvore, selecione 'XML\Atributo'.
8. No campo Nome, digite 'SalesOrder'.
    * SalesOrder  
9. Clique em OK.
10. Clique em Adicionar atributo.
11. No campo Nome, digite 'InvoiceNumber'.
    * InvoiceNumber  
12. Clique em OK.
13. Clique em Adicionar atributo.
14. No campo Nome, digite 'InvoiceAmount'.
    * InvoiceAmount  
15. Clique em OK.
16. Clique em Adicionar para abrir a caixa de diálogo suspensa.
17. Na árvore, selecione 'XML\Elemento'.
18. No campo Nome, digite 'EnclosedDocs'.
    * EnclosedDocs  
19. Clique em OK.
20. Na árvore, selecione 'Fatura\EnclosedDocs'.
21. Clique em Adicionar elemento.
22. No campo Nome, digite 'Documento'.
    * Documento  
23. Clique em OK.
24. Na árvore, selecione 'Fatura\EnclosedDocs\Documento'.
25. Clique em Adicionar para abrir a caixa de diálogo suspensa.
26. Na árvore, selecione 'XML\Atributo'.
27. No campo Nome, digite 'FileName'.
    * FileName  
28. Clique em OK.
29. Clique em Adicionar para abrir a caixa de diálogo suspensa.
30. Na árvore, selecione 'XML\Elemento'.
31. No campo Nome, digite 'FileContent'.
    * FileContent  
32. Clique em OK.
33. Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileContent'.
34. Clique em Adicionar para abrir a caixa de diálogo suspensa.
35. Na árvore, selecione 'Texto\Base64'.
36. Clique em OK.

## <a name="map-format-elements-to-data-model-as-data-source"></a>Mapear elementos de formato para o modelo de dados como fonte de dados
1. Na árvore, selecione 'Fatura\SalesOrder'.
2. Clique na aba Mapeamento.
3. Na árvore, expanda 'modelo'.
4. Na árvore, selecione 'modelo\número da ordem de venda(SalesId)'.
5. Clique em Associar.
6. Na árvore, selecione 'Fatura\InvoiceNumber'.
7. Na árvore, expanda 'modelo\Fatura base(InvoiceBase)'.
8. Na árvore, selecione 'modelo\Fatura base(InvoiceBase)\Número da fatura(ID)'.
9. Clique em Associar.
10. Na árvore, selecione 'Fatura\InvoiceAmount'.
11. Na árvore, selecione 'modelo\Fatura base(InvoiceBase)\Valor da fatura(Valor)'.
12. Clique em Associar.
13. Na árvore, expanda 'modelo\Anexos da fatura'.
14. Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.
15. Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileContent\Base64'.
16. Clique em Associar.
17. Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.
18. Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileName'.
19. Clique em Associar.
20. Na árvore, selecione 'modelo\Anexos da fatura'.
21. Na árvore, selecione 'Fatura\EnclosedDocs\Documento'.
22. Clique em Associar.
23. Clique em Salvar.
24. Feche a página.


