---
title: Criar configurações para gerar documentos com dados da solicitação de emprego
description: Para concluir as etapas neste procedimento, você deve primeiramente concluir o procedimento, ER Gerar documentos com atualização de dados de aplicativo (Parte 1 – Importar configurações).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8376107a33dd83e04f82fcab6847e7f073f08dbc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "316340"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>Criar configurações para gerar documentos com dados da solicitação de emprego

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, ER Gerar documentos com atualização de dados de aplicativo (Parte 1: Importar configurações).



As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico. Neste procedimento, você executa a configuração de formato importado do ER que foi criada para a empresa exemplo, Litware, Inc., para gerar documentos eletrônicos.



Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de DEMF. 



Antes de começar, altere o contexto de país para a empresa de DEMF de DEU (Alemanha) para BEL (Bélgica). Clique em Administração da organização > Organizações > Entidades legais para atualizar o código do país no endereço principal da entidade legal DEMF. Reinicie o aplicativo.


## <a name="run-imported-er-format"></a>Execute o formato de ER importado
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Intrastat (model)'.
3. Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.
4. Clique em Executar.
    * Execute a versão de rascunho de configuração de formato de ER para gerar o relatório Intrastat.  
5. No campo Inserir nome do arquivo, digite 'intrastat.xml'.
    * Especifique o nome do arquivo.  
6. Clique em OK.
    * Revise o arquivo XML gerado.  
7. Feche a página.
8. Vá para Imposto > Declarações > Comércio exterior > Intrastat.
    * Abra este formulário para exibir as transações Intrastat que são incluídas no documento eletrônico gerado.  
9. Clique em Arquivo morto Intrastat.
    * Como o formato de ER executado não contém qualquer configuração para a atualização de dados do aplicativo, os detalhes de relatório Intrastat concluídos não foram arquivados.  
10. Feche a página.
11. Feche a página.

