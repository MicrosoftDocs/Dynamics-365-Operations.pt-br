---
title: Criar uma requisição que use uma RFQ
description: Este artigo explica como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecde250e3517464611b68fe3c960bfbfdf06319
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846001"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Criar uma requisição que use uma RFQ

[!include [banner](../../includes/banner.md)]

Este artigo explica como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF, e você entrar como um Admin para terminar todas as etapas. As tarefas neste guia seriam feitas tipicamente por profissionais da obtenção.


## <a name="create-a-requisition"></a>Criar um requisito
1. No Painel de Navegação, Acesse **Módulos > Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim**.
2. Selecione **Novo**.
3. No campo **Nome**, digite um valor.
4. No campo **Data solicitada**, insira uma data.
5. No campo **Data contábil**, insira uma data.
6. Selecione **OK**.
7. No campo **Motivo**, insira ou selecione um valor.
8. Selecione **Adicionar linha**.
9. No campo **Categoria de compras**, selecione uma categoria na árvore e selecione **OK**.
10. No campo **Nome do produto**, digite um valor.
11. No campo **Quantidade.**, insira um número
12. No campo **Unidade**, insira ou selecione um valor.
13. Selecione **Salvar**.
14. Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.
15. Selecione **Enviar**.
16. Feche a página.
17. Selecione **Enviar**.

## <a name="reassign-a-workflow-task"></a>Reatribuir uma tarefa de fluxo de trabalho
A tarefa seguinte é criar um RFQ para obter ofertas dos vendedores para o produto. Em dados do programa demonstrativo de USMF, os trabalhos da requisição estabelecem-se com uma regra de modo que se um vendedor não está selecionado, ou o preço unitário é 0 para uma linha, uma tarefa será atribuída a um trabalhador específico para criar um RFQ. Para continuar com este guia, você precisa atribuir novamente essa tarefa a um outro usuário (você mesmo). Você pode somente fazer isso se você entrou como um Admin.  

1. Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.
2. Selecione **Exibir histórico**.
3. Atualize a página.
4. Expanda a seção **Rastrear detalhes**.
5. Na árvore, selecione "a linha em que começa com "Linha de fluxo de trabalho ativados em".
6. Selecione **Exibir detalhes do fluxo de trabalho**.
7. Expanda a seção **Itens de trabalho**.
8. Selecione **Reatribuir**.
9. No campo **Usuário**, selecione **Admin**.
10. Selecione **Reatribuir**.
11. Feche as duas páginas.

## <a name="create-an-rfq"></a>Criar um RFQ

1. Atualize a página.
2. Selecione **Solicitação de cotação**.
3. No campo **Comprar entidade legal**, selecione **USMF**. Você deve selecionar a mesma entidade legal que está na linha da requisição.  
4. Na lista, marque a linha selecionada. Se você tiver múltiplas linhas em sua requisição de compra, selecione todas as linhas que você quer adicionar ao RFQ.  
5. Selecione **OK**.
6. Atualize a página.
7. Verifique se o FactBox está aberto e expanda a seção **Documentos relacionados**.
8. Selecione o link no campo **Solicitação de cotação** para abrir o RFQ que acabou de ser criado.
9. Selecione **Cabeçalho**.
10. Selecione **Adicionar**.
11. No campo **Conta de fornecedor**, insira ou selecione um valor.
12. Selecione **Adicionar**.
13. No campo **Conta de fornecedor**, insira ou selecione um valor.
14. Selecione **Enviar**.
15. Selecione **OK**.
16. Selecione **Digitar Resposta**.
17. No Painel de Ação, selecione **Responder**.
18. Selecione **Copiar Dados para Resposta**. Isto copia dados, tais como a quantidade e as datas, do RFQ à resposta.  
19. No campo **Preço unitário**, insira um número. Este é o preço que você recebeu do vendedor. Você pode querer também inserir informações adicionais do vendedor.  
20. Selecione **Aceitar**.
21. Selecione **OK**.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Verifique se o fornecedor e o preço foram transferidos para a requisição
1. Feche a página.
2. Selecione **Linhas**.
3. Selecione **Informações Relacionadas**.
4. Selecione **Requisição de Compra**.
5. Selecione a linha que foi transferida ao RFQ. Verifique se o preço e o vendedor estão copiados à requisição.  
6. Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.
7. Selecione Concluído.
8. Selecione a página.
9. Selecione Concluído.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]