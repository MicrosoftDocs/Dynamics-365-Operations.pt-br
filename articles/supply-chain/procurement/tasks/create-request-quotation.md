--- 
title: "Criar uma solicitação de cotação"
description: "Este procedimento mostra como criar uma solicitação de cotação."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 331f516f3483acd79be4ef7b95b53adcfbef1ae2
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-request-for-quotation"></a>Criar uma solicitação de cotação

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma solicitação de cotação. Isso seria feito normalmente por um agente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Você precisa ter tipos de solicitação configurados antes de começar. Depois de concluir essa tarefa e você tiver criado e enviado uma RFQ, você pode digitar as respostas por fornecedor, compará-las e premiar o contrato.


## <a name="prepare-a-new-rfq"></a>Preparar uma nova RFQ
1. Vá para Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.
2. Clique em Novo.
    * Os seguintes tipos de compra estão disponíveis: Ordem de compra (este é o padrão): um documento que confirma a oferta para comprar produtos, ou a aceitação de uma oferta para vender produtos em troca de pagamento. Requisição de compra: esse tipo é selecionado automaticamente ao criar uma RFQ diretamente de uma requisição de compra. Se você selecionar essa opção manualmente, receberá uma mensagem de erro. Contrato de compra: um contrato para comprar uma quantidade ou um valor específico de produtos ao longo do tempo. Se você selecionar esta opção, selecione o intervalo de datas que se aplica ao contrato de compra.  
3. No campo Título do documento, digite um valor.
4. No campo Tipo de solicitação, insira ou selecione um valor.
    * Se um método de pontuação estiver associado ao tipo de solicitação, esse será o método de pontuação padrão para a RFQ que você estiver criando. Será possível alterar o método de pontuação posteriormente.  
    * No campo Data de entrega, insira uma data.  
    * Selecione a data na qual você deseja receber os itens.  
    * No campo Data de vencimento e hora, insira uma data e hora.  
    * Especifique a data e a hora em que os fornecedores deverão responder à RFQ.  
5. No campo Depósito, insira ou selecione um valor.
    * O endereço de entrega usará como padrão o endereço do depósito.  
6. Clique em OK.

## <a name="add-lines"></a>Adicionar linhas
    * Depois de ter especificado as informações básicas sobre sua RFQ, você especificará os bens ou serviços para os quais deseja que os fornecedores façam ofertas. Item é o tipo de linha padrão.   
1. No campo Número do item, insira ou selecione um valor.
    * Se você estiver usando USMF, é possível selecionar T0020.  
2. No campo Quantidade, insira um número.
3. Clique em Adicionar linha.
4. No campo Tipo de linha, selecione 'Categoria'.
    * Você pode usar o tipo de linha de categoria para criar solicitação de cotação por mercadorias ou serviços não provenientes do estoque. Você precisa depois selecionar o tipo de mercadorias ou serviços de uma hierarquia das categorias de aquisição.  
5. No campo Categoria de compras, insira ou selecione um valor.
6. No campo Nome do produto, digite um valor.
7. No campo Quantidade, insira um número.
8. No campo Unidade, insira ou selecione um valor.

## <a name="add-vendors"></a>Adicionar fornecedores
1. Clique no Cabeçalho para alterar a exibição das linhas da exibição do cabeçalho. 
2. Expandir a seção Fornecedor.
3. Clique em Adicionar fornecedores automaticamente.
    * Você poderá adicionar fornecedores à RFQ automaticamente, com base na categoria de compras dos itens solicitados. Se não houver um fornecedor aprovado para as categorias incluídas nas linhas, você pode adicionar fornecedores manualmente.  
4. Clique em Adicionar.
5. No campo Conta de fornecedor, insira ou selecione um valor.
6. Clique em Adicionar.
7. No campo Conta de fornecedor, insira ou selecione um valor.
    * Depois de selecionar um fornecedor, o status é Criado. Isso significa que as informações do fornecedor foram salvas na RFQ, mas você não enviou a RFQ para o fornecedor. Você pode adicionar um fornecedor a uma RFQ independentemente do status do fornecedor.  

## <a name="send-the-rfq-to-vendors"></a>Envie a RFQ aos fornecedores
1. Clique em Enviar.
    * Na página Enviando solicitação de cotação, verifique se os fornecedores na lista são aqueles que você deseja que recebem a RFQ.  
2. Clique em Imprimir.
    * Esta caixa de diálogo permite que você imprima a RFQ. Se você optar por imprimir uma folha de respostas, o conteúdo desta é definido nos parâmetros de aquisição e de fornecimento. Para escolher como imprimir folhas de respostas, depois que você abrir a caixa de diálogo de impressão, clique em Opções avançadas de impressão. Uma RFQ será impressa para cada fornecedor, contendo as linhas que têm o status de criado ou de enviado. As linhas canceladas e as linhas com respostas registradas não serão impressas.   
3. Clique em Cancelar.
4. Clique em OK.
5. Feche a página.
6. Feche a página.

## <a name="view-the-rfq-journal"></a>Exibir o diário da RFQ
1. Vá para Aquisição e fornecimento > Solicitações de cotação > Acompanhamento de solicitações de cotação > Diários de solicitações de cotação.
2. Clique em Visualizar/Imprimir.
3. Clique em Exibição original.
4. Feche a página.
5. Feche a página.


