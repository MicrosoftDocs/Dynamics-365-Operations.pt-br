--- 
title: Criar e processar uma conformidade
description: "Use este procedimento para executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4082caf2cc8393345d4f79a991f2cf205b06b142
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-process-a-conformance"></a>Criar e processar uma conformidade

[!include[task guide banner](../../includes/task-guide-banner.md)]

Use este procedimento para executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente. Você pode executar esse registro na empresa de demonstração USMF e pode usar os valores sugeridos. Normalmente, esse procedimento é realizado por um encarregado de qualidade.  Como um pré-requisito, execute o registro de tarefa “Inspecionar a qualidade das mercadorias“. Para processar a aprovação de uma não conformidade, o usuário que executa o registro de tarefa deve ter um valor de “Nome“ atribuído na página Usuários. Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário. 


## <a name="select-a-quality-order"></a>Selecione uma ordem de qualidade
1. Vá para Ordens de qualidade.
2. Na lista, marque a linha selecionada.
    * Selecione a ordem de qualidade que foi criada no registro de tarefa "Inspecionar a qualidade das mercadorias".  

## <a name="create-a-nonconformance"></a>Criar uma não conformidade
1. Clique em Consultas.
2. Clique em Não conformidades.
3. Clique em Novo.
4. No campo Tipo de problema, clique no botão suspenso para abrir a pesquisa.
    * Selecione o problema encontrado durante o processo de inspeção.  
5. No campo Tipo de problema, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.
8. Clique em OK.

## <a name="approvereject-a-nonconformance"></a>Aprovar/rejeitar uma não conformidade
1. Clique em Funções.
2. Clique em Aprovar a não conformidade.
    * Para esse exemplo, aprove a não conformidade. Não conformidades aprovadas podem ser associadas às operações relacionadas para registrar o trabalho que é feito como parte do manuseio da não conformidade e, como nesse registro de tarefa, o processamento do manuseio de correção.  
3. Clique em Sim.

## <a name="create-a-correction-action"></a>Criar uma ação de correção
1. Clique em Correções.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Número dos funcionários, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
6. Clique em Selecionar.
7. Clique em Anexar.
    * Crie uma nota sobre a correção. Neste exemplo, a ação é entrar em contato com o fornecedor para discutir o caso não conformidade.  
8. Clique em Novo.
9. Clique em Nota.
    * Observe que, dependendo da configuração do relatório, diferentes tipos de documentos podem ser impressos em relatórios relacionados ao gerenciamento de não conformidades.  
10. No campo Descrição, digite um valor.
11. Feche a página.

## <a name="maintain-a-correction"></a>Manter uma correção
1. Clique em Marcar como completo.
2. Clique em OK.
3. Feche a página.

## <a name="close-a-nonconformance"></a>Fechar uma não conformidade
1. Clique em Funções.
2. Clique em Fechar a não conformidade.
3. Clique em Sim.
4. Feche a página.
5. Feche a página.


