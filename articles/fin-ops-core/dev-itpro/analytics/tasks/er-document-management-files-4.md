---
title: O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 4 - executar formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico para usar arquivos de gerenciamento de documentos na saída de ER. (Parte 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a7c9705d8b53ef13cd3faf13290f3f1b1d1c43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749108"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a>O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 4 - executar formato)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER. Essas etapas podem ser executadas na empresa DEMF.

Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 3: criar formato)".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Adicionar os anexos necessários para a ordem de venda de uma única fatura
1. Vá para Contas recebíveis > Faturas > Faturas de cliente abertas.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Fatura com um valor de 'CIV-000148'.
    * CIV-000148  
3. Clique para seguir o link da fatura selecionada.
    * CIV-000148  
4. Clique para seguir o link no campo Ordem de venda.
    * 000148  
5. No campo Linhas ou cabeçalho, selecione a opção de Cabeçalho.
    * Selecione Cabeçalho para indicar que este será o alvo para a adição de anexos.  
6. Clique em Anexar.
    * Adicione alguns arquivos como anexos a esta ordem de venda. Use os arquivos dos tipos de documento que têm suporte do gerenciamento de documentos (com extensões de arquivo DOCX, DPF XML JPG, etc.). Procure e selecione os arquivos a serem anexados e processados com a fatura relacionada na mensagem eletrônica do ER.  
7. Clique em Novo.
8. Clique em Arquivo.
9. Clique em Novo.
10. Clique em Arquivo.
11. Feche a página.
12. Feche a página.
13. Feche a página.
14. Feche a página.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Executar relatório criado para a fatura selecionada
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Modelo de fatura de cliente'.
3. Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.
4. Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.
5. Clique em Executar.
6. Expanda os Registros para incluir a seção ().
7. Clique em Filtro.
8. Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.
9. No campo Critérios, digite '000148'.
    * No campo do critério "Ordem de venda" digite o número de ordem 000148.  
10. Clique em OK.
11. Clique em OK.
    * Revise a saída gerada. Observe que um único nó XML foi criado para cada anexo. O conteúdo do anexo é preenchido na saída do XML no formato de texto MIME (base64).  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]