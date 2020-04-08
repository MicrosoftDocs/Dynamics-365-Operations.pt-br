---
title: Criar uma requisição para consumo
description: Este tópico descreve o processo de criação de uma requisição.
author: mkirknel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ca44b4793f61d1067b9e0740b9a447d3a2363c2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147379"
---
# <a name="create-a-requisition-for-consumption"></a>Criar uma requisição para consumo

[!include [banner](../../includes/banner.md)]

Este tópico descreve o processo de criação de uma requisição. Mostra as diferentes formas de pesquisar por produtos no catálogo de aquisições e como adicionar um produto que não está no catálogo. Antes de iniciar esse procedimento, você deve ter uma política de compras configurada com Consumo como o tipo padrão de requisição. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. O procedimento só pode ser realizado por um perfil de usuário configurado como funcionário. Essa tarefa é normalmente realizada por um funcionário. O **Funcionário** usa função de segurança irá permitir que você realize as tarefas. Ou, se você estiver usando USMF, poderá fazer logon como **Alicia**.


## <a name="create-a-new-requisition"></a>Criar uma nova requisição
1. Vá para **Painel de navegação > Módulos > Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim**.
2. Selecione **Novo**.
3. No campo **Nome**, forneça o nome da requisição.
4. No campo **Data solicitada**, insira uma data. Por padrão, a data de solicitação e a data contábil são copiadas para as linhas de requisição de compra. Elas podem ser alteradas no nível da linha. A data de solicitação é a data de entrega da solicitação.  
5. No campo **Data contábil**, insira uma data. A data contábil é usada para registrar a entrada contábil na contabilidade e para validar se os fundos de orçamento estão disponíveis.  
6. Selecione **OK**.
7. No campo **Motivo**, selecione uma opção no menu suspenso. Por padrão, o motivo de justificativa de negócio selecionado é exibido para as linhas de requisição de compra, mas você pode alterá-lo no nível da linha.  
8. Selecione o motivo.
9. No campo **detalhes**, insira uma justificativa mais descritiva para a requisição.

## <a name="add-a-line-to-the-requisition"></a>Adicionar uma linha à requisição
1. Selecione **Adicionar linha**. Existem duas maneiras de adicionar linhas à requisição de compra. Se você sabe o número do produto ou sabe que está solicitando um produto que não está no catálogo de produtos, pode adicionar a linha diretamente com **Adicionar linha**. A outra forma é utilizar **Adicionar produtos** em que é possível usar pesquisa e filtragem para localizar itens no catálogo de produtos.    
2. Selecione a linha recém-criada.
    - O solicitante é o funcionário que solicitou a requisição.   
    - Por padrão a pessoa que prepara a requisição é o funcionário que a solicitou. Você precisa receber permissão para preparar uma linha de requisição em nome de outro funcionário. Se você possuir tais permissões então os outros funcionários aparecerão nessa pesquisa.  
3. No campo **Número de item**, digite um valor. Os itens disponíveis para escolha são delimitados pela política de acesso a categoria e pelo catálogo de aquisições para a pessoa jurídica compradora.   
4. No campo **Quantidade.**, insira um número

## <a name="add-more-products-to-the-requisition"></a>Adicionar mais produtos à requisição
1. Selecione **Adicionar produtos**. Essa é a opção na qual você pode pesquisar por produtos no catálogo de produtos.    
2. No campo **Localizar nó da categoria de compras**, insira a primeira parte do nome da categoria que você está procurando e selecione **Inserir**. Por exemplo, insira `comput`.  
3. Use o atalho **InvokeDefaultButton**.
4. Utilize o **Filtro** para filtrar a lista de produtos na categoria selecionada.
5. Selecione a carta de produtos que você deseja adicionar à requisição.
6. Selecione **Adicionar a linhas**.
7. No campo **Quantidade.**, insira um número
8. No campo **Localizar nó da categoria de compras**, digite a primeira parte do nome da categoria que você está procurando e selecione **Inserir**. Por exemplo, insira `High` (marca-textos).  
9. Use o atalho **InvokeDefaultButton**.
10. Selecione **Adicionar produtos não listados às linhas** para adicionar um produto que não está listado no catálogo de aquisições.
11. No campo **Nome do produto**, digite um valor.
12. No campo **Unidade**, digite um valor.
13. Selecione **OK**.
14. No campo **Descrição do item**, adicione uma descrição do produto.
15. No campo **Quantidade.**, insira um número
16. No campo **Preço unitário**, insira um número. Se você sabe o preço de um fornecedor específico (que você seleciona no campo conta de fornecedor), esse preço pode ser inserido.   
17. No campo **Conta de fornecedor**, abra a lista suspensa para selecionar uma opção. Os fornecedores que estão disponíveis neste campo dependem das políticas de compras e do status que o fornecedor tem para a categoria de aquisição atual. Em vez de selecionar um fornecedor aqui, outra alternativa é selecionar **Sugerir fornecedor**.    
18. Na lista, selecione o fornecedor que deseja utilizar.
19. No campo **Número do item externo**, digite um valor. Este é um número de referência para o produto que é conhecido pelo fornecedor. Por exemplo, isso poderia ser o número de item do produto no catálogo do próprio fornecedor.  
20. Selecione **OK**.

## <a name="distribute-amounts"></a>Distribuir valores
1. Selecione **Finanças**.
2. Selecione **Distribuir valores**. Este processo mostra como distribuir os custos da primeira linha entre 2 contas. Isso também pode ser feito mais tarde durante a revisão da requisição.  
3. Selecione **Dividir** para criar uma nova linha de distribuição.
4. No campo **Conta contábil** selecione o primeiro centro de custo que deve receber parte do custo.
5. Selecione a outra linha de distribuição.
6. No campo Conta contábil especifique o outro centro de custo.
7. Selecione **Distribuir igualmente**.
8. Feche a página.

## <a name="view-line-details"></a>Exibir detalhes de linha
1. Ative/desative a expansão da seção **Detalhes de linha**.

## <a name="submit-the-requisition"></a>Enviar a requisição
1. Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.
2. Selecione **Enviar**.
3. Feche a página.
4. No campo **Comentário**, digite uma nota para o aprovador da requisição.
5. Selecione **Enviar**.
6. Feche a página.
7. Atualize a página.

