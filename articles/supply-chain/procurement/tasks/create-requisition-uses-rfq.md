---
title: Criar uma requisição que use um RFQ
description: Este guia mostra como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a9418b526f992008086f10ce78e95cb682bc164
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547390"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Criar uma requisição que use um RFQ

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia mostra como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF, e você entrar como um Admin para terminar todas as etapas. As tarefas neste guia seriam feitas tipicamente por profissionais da obtenção.


## <a name="create-a-requisition"></a>Criar um requisito
1. Vá para Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Data de solicitação, insira uma data.
5. No campo Data contábil, insira uma data.
6. Clique em OK.
7. No campo Motivo, insira ou selecione um valor.
8. Clique em Adicionar linha.
9. No campo da categoria da obtenção, selecione uma categoria na árvore, e clique então em OK.
10. No campo Nome do produto, digite um valor.
11. No campo Quantidade, insira um número.
12. No campo Unidade, insira ou selecione um valor.
13. Clique em Salvar.
14. Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.
15. Clique em Enviar.
16. Feche a página.
17. Clique em Enviar.

## <a name="reassign-a-workflow-task"></a>Reatribuir uma tarefa de fluxo de trabalho
    * A tarefa seguinte é criar um RFQ para obter ofertas dos vendedores para o produto. Em dados do programa demonstrativo de USMF, os trabalhos da requisição estabelecem-se com uma regra de modo que se um vendedor não está selecionado, ou o preço unitário é 0 para uma linha, uma tarefa será atribuída a um trabalhador específico para criar um RFQ. Para continuar com este guia, você precisa atribuir novamente essa tarefa a um outro usuário (você mesmo). Você pode somente fazer isso se você entrou como um Admin.  
1. Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.
2. Clique em Exibir histórico.
3. Atualize a página.
4. Expanda a seção Rastrear detalhes.
5. Na árvore, selecione 'a linha em que começa com "Linha de fluxo de trabalho ativados em"'.
6. Clique em Exibir detalhes do fluxo de trabalho.
7. Expanda a seção Itens de trabalho.
8. Clique em Reatribuir.
9. No campo Usuário, selecione Admin.
10. Clique em Reatribuir.
11. Feche a página.
12. Feche a página.

## <a name="create-an-rfq"></a>Criar um RFQ
1. Atualize a página.
2. Clique em Solicitação de cotação.
3. No campo Comprar entidade legal, selecione USMF.
    * Você deve selecionar a mesma entidade legal que está na linha da requisição.  
4. Na lista, marque a linha selecionada.
    * Se você tiver múltiplas linhas em sua requisição de compra, selecione todas as linhas que você quer adicionar ao RFQ.  
5. Clique em OK.
6. Atualize a página.
7. Abra o Quadro de Fatos e expanda então a seção Relacionada dos documentos.
    * Você pode já ter aberto o Quadro de Fatos. Procure o ícone com uma seta nela, à direita dos botões de alavanca das linhas/cabeçalho. Se a seta está apontando à direita, o Quadro de Fatos já está aberto. Se a seta aponta à esquerda, clique-a para abrir o Quadro de Fatos.  
8. Clique no link no campo Solicitação de cotação para abrir o RFQ que acabou de ser criado.
9. Clique em Cabeçalho.
10. Clique em Adicionar.
11. No campo Conta de fornecedor, insira ou selecione um valor.
12. Clique em Adicionar.
13. No campo Conta de fornecedor, insira ou selecione um valor.
14. Clique em Enviar.
15. Clique em OK.
16. Clique em Digitar Resposta.
17. No Painel de Ação, clique em Resposta.
18. Clique em Copiar dados para resposta.
    * Isto copia dados, tais como a quantidade e as datas, do RFQ à resposta.  
19. No campo Preço unitário, insira um número.
    * Este é o preço que você recebeu do vendedor. Você pode querer também inserir informações adicionais do vendedor.  
20. Clique em Aceitar.
21. Clique em OK.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Verifique se o fornecedor e o preço foram transferidos para a requisição
1. Feche a página.
2. Clique em Linhas.
3. Clique em Informações Relacionadas.
4. Clique em Linhas de requisição de compra.
5. Selecione a linha que foi transferida ao RFQ.
    * Verifique se o preço e o vendedor estão copiados à requisição.  
6. Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.
7. Clique em Concluir.
8. Feche a página.
9. Clique em Concluir.

