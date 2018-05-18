--- 
title: "Inserir e comparar lances RFQ e contratos de prêmio"
description: "Este procedimento mostra como inserir respostas de uma solicitação de cotação, marcar e comparar ofertas, além de conceder a oferta a um dos fornecedores."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Inserir e comparar lances RFQ e contratos de prêmio

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como inserir respostas de uma solicitação de cotação, marcar e comparar ofertas, além de conceder a oferta a um dos fornecedores. Você pode usar este procedimento na empresa USMF de dados de demonstração. Antes de começar, você deve ter uma RFQ com duas linhas que foi enviado para pelo menos dois fornecedores. Você pode executar o procedimento "Criar uma solicitação de cotação" como um pré-requisito para criar isso. Você precisa ter configurado critérios de pontuação antes de executar este procedimento.


## <a name="enter-a-reply-from-a-vendor"></a>Inserir uma resposta de um fornecedor
1. Vá para Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.
2. Selecione uma solicitação de cotação com um status Enviado e clique no link no número do caso da Solicitação de cotação.
    * A RFQ deve ser enviada para, pelo menos, 2 fornecedores.  
3. Clique no cabeçalho para ir para a lista de fornecedores.
4. Selecione o fornecedor para o qual você deseja inserir uma resposta no RFQ.
5. Clique em Digitar Resposta.
6. No Painel de Ação, clique em Resposta.
7. Clique em Copiar dados para resposta.
    * Esta ação copiará os dados selecionados, por exemplo, a quantidade de exemplos da solicitação de cotação para a resposta à solicitação de cotação. Alternativamente você pode ignorar essa ação e preencher toda a resposta do campo manualmente ao editar a resposta.  
8. Clique em Editar.
9. No campo Preço unitário, insira um número.
10. Escolher a outra linha de cotação.
11. No campo Preço unitário, insira um número.

## <a name="score-the-bid"></a>Marcar a oferta
1. Clique no cabeçalho para ir para a pontuação do lance.
2. Expanda a seção de pontuação do lance.
3. No campo Pontuação, insira um número para um dos critérios de marcação.
    * Se você passar o mouse em cima de um critério de pontuação, uma dica de ferramenta exibe a variação da pontuação que você precisa usar. Nesta demonstração você pode adicionar um número entre 1 e 5 para qualquer um dos critérios.  
4. Selecione outro critério para marcação.
5. No campo Pontuação, insira um número.
6. Expanda a seção de Questionários.
    * Se os exemplos do caso RFQ apresentarem um questionário que foi enviado aos fornecedores, você pode inserir suas respostas na seção de questionário.  
7. Feche a página.

## <a name="enter-a-reply-for-another-vendor"></a>Insira uma resposta de outro fornecedor
1. Selecione o fornecedor seguinte limpando o fornecedor que você contatou apenas na resposta para selecionar e na linha do fornecedor a seguir.
2. Na lista, localize e selecione o PDV desejado.
3. Clique em Digitar Resposta.
4. Clique em Copiar dados para resposta.
5. Clique em Editar.
6. No campo Preço unitário, insira um número.
7. Escolher a outra linha de cotação.
8. No campo Preço unitário, insira um número.

## <a name="score-the-second-bid"></a>Marcar a segunda oferta
1. Clique no cabeçalho para ir para a pontuação do lance.
2. No campo Pontuação, insira um número.
3. Na lista, localize e selecione o PDV desejado.
4. No campo Pontuação, insira um número.

## <a name="compare-the-replies"></a>Comparar as respostas
1. No Painel de Ação, clique em Geral.
2. Clique em Comparar Respostas.
3. No campo Pontuação, insira um número.
    * Esta página mostra as ofertas com o cabeçalho e as linhas, e a pontuação total em nível de cabeçalho. Você pode comparar as linhas de classificação na grade de forma que as linhas comparáveis sejam próximas uma da outra. As informações também incluem: Quantidade: a quantidade cotada pelo fornecedor. Isso pode não ser igual à quantidade especificada na RFQ.   Valor líquido: o preço cotado por um fornecedor, depois de subtrair descontos, para os itens na linha.   Desvio: o número de dias em que a data de vencimento no cabeçalho ou a linha da oferta desvia da data de entrega solicitada no cabeçalho ou na da RFQ.   Você só pode inserir uma classificação para cada lance.  
4. Selecione a linha do cabeçalho do outro lance que deseja pontuar.
5. No campo Pontuação, insira um número.
6. Clique em Salvar.

## <a name="reject-a-bid"></a>Rejeitar uma oferta
1. Selecione a linha do cabeçalho do lance que deseja rejeitar
    * Você só pode aceitar, rejeitar, ou devolver um lance ou linhas dentro de um lance por vez.  
2. Marque a caixa de seleção Marcar.
    * Se você marcar a caixa de seleção do cabeçalho da oferta, então todas as linhas serão marcadas também. Você também pode optar por marcar um subconjunto de linhas na oferta para aceitar ou rejeitar. É possível aceitar uma oferta de fornecedor para algumas linhas de uma solicitação de cotação, e permissões em outras linhas RFQ de outro fornecedor, eles podem precisar fazer isso em 2 etapas, oferecidas uma por vez. Se as linhas alternativas estiverem presentes, você só poderá aceitar a linha de oferta original ou sua alternativa, mas não ambas.  
3. Clique em Rejeitar.
4. Clique em Parâmetros para abrir a caixa de diálogo suspensa.
5. No campo Motivo da rejeição, insira ou selecione um valor.
    * O motivo para a rejeição será armazenado na resposta.  
6. Clique em OK.
7. Clique em OK.
8. Feche a página.
9. Feche a página.
10. Atualize a página.

## <a name="accept-a-bid"></a>Aceitar uma oferta
1. Selecione a oferta que deseja aceitar e clique no link no campo Solicitação de cotação.
2. No Painel de Ação, clique em Resposta.
3. Clique em Aceitar.
    * Se você marcou linhas específicas e não outras, então a ação de aceitação incluirá somente as linhas marcadas. Se você deseja aceitar todas as linhas da oferta então você não precisará marcar as linhas.  
4. Clique em Parâmetros para abrir a caixa de diálogo suspensa.
    * Isso permite que você registre um motivo para aceitar a oferta. O motivo para será armazenado no lance.  
5. No campo Motivo da aceitação, insira ou selecione um valor.
6. Clique em OK.
7. Clique em OK.
    * Quando você clicar em OK, isso gera uma ordem de compra com base nas linhas que estão incluídas na aceitação da solicitação de cotação. Se houver outras ofertas que não foram processadas (aceitas, rejeitadas ou retornadas), então o sistema avisará você para rejeitar ofertas restantes.  

## <a name="view-the-purchase-order-thats-been-generated"></a>Ver a ordem de compra que foi gerada
1. No Painel de Ação, clique em Geral.
2. Clique em Ordem de compra.
    * Aqui você pode ver a ordem de compra que foi gerada quando aceitou a oferta.  
3. Feche a página.
4. Feche a página.
5. Feche a página.
6. Feche a página.


