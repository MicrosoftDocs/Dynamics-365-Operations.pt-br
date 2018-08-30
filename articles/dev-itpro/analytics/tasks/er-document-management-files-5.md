--- 
title: "Modificar e executar formatos para usar arquivos de gerenciamento de documentos em saídas de ER"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: 5effbecf98e633d07f9e5eb22d3df1a12967c1e4
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="modify-and-run-formats-to-use-document-management-files-in-er-output"></a>Modificar e executar formatos para usar arquivos de gerenciamento de documentos em saídas de ER

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER. Essas etapas podem ser executadas na empresa DEMF.

Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 4): executar formato".

Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>Modificar o formato para popular anexos para a geração de mensagens no formato binário
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Modelo de fatura de cliente'.
3. Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.
4. Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.
5. Clique em Designer.
    * Você preencherá a mensagem da fatura na saída gerada como um arquivo XML usando a codificação UNICODE.  
6. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
7. Na árvore, selecione 'Comum\Arquivo'.
8. No campo Nome, digite 'Mensagem Xml'.
    * Mensagem Xml  
9. No campo Codificação, digite 'UTF-8'.
    * UTF-8  
10. Clique em OK.
    * Configurar as saídas geradas como arquivo compactado.  
11. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
12. Na árvore, selecione 'Comum\Pasta'.
13. No campo Nome, digite 'Saída Zip'.
    * Saída Zip  
14. Clique em OK.
15. Na árvore, selecione 'Saída Zip'.
    * Adicionar anexos ao arquivo compactado gerado como arquivos com extensões e nomes originais.  
16. Clique em Adicionar para abrir a caixa de diálogo suspensa.
17. Na árvore, selecione 'Comum\Arquivo'.
18. No campo Nome, digite 'Arquivo anexo'.
    * Arquivo anexo  
19. Clique em OK.
20. Na árvore, selecione 'Saída Zip\Arquivo anexo'.
21. Clique em Adicionar para abrir a caixa de diálogo suspensa.
22. Na árvore, selecione 'Texto\Base64'.
23. Clique em OK.

## <a name="map-new-format-elements-to-data-model"></a>Mapear novos elementos de formato no modelo de dados
1. Clique na aba Mapeamento.
2. Na árvore, expanda 'modelo'.
3. Na árvore, expanda 'modelo\Anexos da fatura'.
4. Na árvore, selecione 'Saída Zip\Arquivo anexo\Base64'.
5. Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.
6. Clique em Associar.
7. Na árvore, selecione 'Saída Zip\Arquivo anexo'.
8. Clique em Editar nome do arquivo.
9. Na árvore, expanda 'modelo'.
10. Na árvore, expanda 'modelo\Anexos da fatura'.
11. Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.
12. Clique em Adicionar fonte de dados.
13. Clique em Salvar.
14. Feche a página.
15. Na árvore, selecione 'modelo\Anexos da fatura'.
16. Clique em Associar.
17. Clique em Salvar.
18. Feche a página.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Executar relatório criado para a fatura selecionada
1. Clique em Executar.
2. Expanda os Registros para incluir a seção ().
3. Clique em Filtro.
4. Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.
5. No campo Critérios, no campo do critério "Ordem de venda" digite o número de ordem 000148.
    * 000148  
6. Clique em OK.
7. Clique em OK.
    * Revise a saída gerada. Observe que, além da mensagem da fatura em formato XML, um único arquivo foi criado para cada anexo. Os arquivos anexos são preenchidos com as saídas compactadas em formato binário.  


