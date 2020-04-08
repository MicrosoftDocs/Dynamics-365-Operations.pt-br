---
title: Inserir e comparar lances RFQ e contratos de prêmio
description: Este tópico explica como inserir respostas de uma solicitação de cotação (RFQ), marcar e comparar ofertas, além de premiar o contrato a um dos fornecedores.
author: mkirknel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 888b8ea8a4ca0c48706442308309588bf25d47d9
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149541"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Inserir e comparar lances RFQ e contratos de prêmio

[!include [banner](../../includes/banner.md)]

Este tópico explica como inserir respostas de uma solicitação de cotação (RFQ), marcar e comparar ofertas, além de premiar o contrato a um dos fornecedores. Você pode usar este procedimento na empresa **USMF** de dados de demonstração.

Antes de iniciar esse procedimento, você deve ter uma RFQ com duas linhas que foi enviado para pelo menos dois fornecedores. Para criar esse RFQ, preencha o procedimento [Criar uma solicitação de cotação](create-request-quotation.md). Os critérios de pontuação também devem ser configurados antes que você possa concluir esse procedimento.

É possível inserir o lance como um fornecedor ou um profissional de compras. Para obter mais informações, consulte [Configurar e manter colaboração de fornecedor](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Inserir uma resposta como um fornecedor

1. No painel, selecione **Lances de fornecedor**.
2. Na lista **Novos convites de lances**, encontre uma RFQ que acabou de ser enviada. Selecione a RFQ para revisar o que foi solicitado.
3. Selecione **Anexos de RFQ** para revisar todos os anexos que foram adicionados.
4. Selecione **Lance** para tornar os campos editáveis. Observe que o campo **Andamento do lance** está definido como **Fornecedor está atualizando**.
5. No cabeçalho e nas linhas, insira os valores da resposta do lance.
6. Se algum anexo precisar ser adicionado ao lance, selecione **Anexos de lances**.
7. Selecione a Guia Rápida **Itens de orientação de lances** para verificar se algum documento é necessário.
8. Selecione a Guia Rápida **Amendments** para verificar se a RFQ foi corrigida.
9. Selecione a Guia Rápida **Questionário**. Quaisquer questionários que apareçam aqui devem ser respondidos.
10. Selecione a Guia Rápida **Detalhes da linha** para exibir informações estendidas sobre a linha.
11. Selecione **Redefinir de RFQ** somente para redefinir os valores inseridos nos valores originais da RFQ.
12. Você pode salvar o lance a qualquer momento e fazer processamento adicional posteriormente, desde que a data e a hora de expiração não tenham passado. Nesse caso, você pode localizar o lance na lista **Lances em andamento** no espaço de trabalho **Lances de fornecedor**.
13. Quando o lance estiver pronto para ser enviado, selecione **Enviar**. Se não quiser fazer o lance, selecione **Recusar**. Os lances enviados estão disponíveis na lista **Lances enviados** no espaço de trabalho **Lances de fornecedor**.  
14. Depois que o lance é enviado, você pode recuperá-lo a qualquer momento antes da data e hora de vencimento. Observe que quando um lance é recuperado, ele não é tratado como enviado. Quando o lance é aceito ou rejeitado pelo departamento de compras, ele aparece na lista **Lances concedidos** ou **Lances perdidos** no espaço de trabalho **Lances de fornecedor**.  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Inserir a resposta de um fornecedor como profissional de compras

1. Certifique-se de que a permissão para editar os lances de fornecedores esteja configurada. Vá para **Compras e fornecimento \> Configuração \> Parâmetros de compras**. Na guia **Solicitação de cotação**, defina a opção **O comprador pode editar o lance de fornecedores** como **Sim**.
2. Vá para **Aquisição e fornecimento \> Solicitações de cotação \> Todas as solicitações de cotação**.
3. Selecione uma RFQ com um status **Enviado** e depois o link no campo **Caso de solicitação de cotação**.
4. Selecione **Gerenciar respostas**. A página que aparece mostra uma RFQ para cada fornecedor que foi convidado para o lance.
5. Selecione uma RFQ que não foi respondido. (O campo **Andamento de resposta** deve ser definido como **Não iniciado**.)
6. Selecione **Editar \> Editar resposta de RFQ**. A página **Resposta de RFQ** é exibida. Como profissional de compras, você pode inserir a resposta em nome do fornecedor. Observe que o campo **Andamento do lance** está definido como **Comprador está atualizando**.  
7. Insira os dados do lance. Quando terminar, selecione **Enviar**.

## <a name="score-the-bids"></a>Marcar os lances

1. Na página **Todas as solicitações de cotação**, selecione o caso de RFQ para o qual deseja pontuar as respostas.
2. Selecione **Gerenciar respostas**.
3. Selecione a resposta a ser pontuada.
4. Selecione **Cabeçalho** para que você possa visualizar a pontuação do lance.
5. Na Guia Rápida **Pontuação do lance**, insira um número no campo **Pontuação** para um dos critérios de marcação. Se você passar o mouse sobre um critério de pontuação, uma dica de ferramenta mostrará o intervalo em que a pontuação deve estar. Nesta demonstração, você pode inserir um número entre 1 e 5 para qualquer um dos critérios de pontuação.  
6. Repita a etapa 5 para outro critério de pontuação.
7. Se o caso de RFQ tiver um questionário que foi enviado aos fornecedores, você poderá inserir as respostas do fornecedor na Guia Rápida **Questionários**.
8. Feche a página.
9. Repita as etapas 1 a 8 para todos os outros lances.

## <a name="compare-the-replies"></a>Comparar as respostas

1. No Painel de ações, na guia **Geral**, selecione **Comparar respostas**.
2. No campo **Classificação**, insira um número.  
    - Esta página mostra os lances, juntamente com as informações de cabeçalho e linha, e também a pontuação total no nível do cabeçalho. Você pode comparar as linhas classificando a grade de forma que as linhas comparáveis sejam próximas uma da outra. As seguintes informações também estão incluídas:
    - **Quantidade** – A quantidade que o fornecedor cotou. Essa quantidade pode não ser igual à quantidade especificada na RFQ.
    - **Valor líquido** – O preço que o fornecedor cotou para os itens na linha, menos os descontos.
    - **Desvio** – O número de dias em que a data de entrega no cabeçalho ou na linha do lance difere da data de entrega solicitada no cabeçalho ou na linha da RFQ. Você só pode inserir uma classificação para cada lance.  
3. Selecione a linha do cabeçalho do outro lance que deseja pontuar.
4. No campo **Classificação**, insira um número.
5. Selecione **Salvar**.

## <a name="reject-a-bid"></a>Rejeitar uma oferta

1. Selecione a linha do cabeçalho do lance que deseja rejeitar Você pode aceitar, rejeitar ou devolver apenas um lance ou as linhas em apenas um lance por vez.
2. Marque a caixa de seleção **Marcar**.  
    - Se você marcar a caixa de seleção **Marcar** no cabeçalho do lance, todas as linhas também serão marcadas. Para rejeitar ou aceitar apenas algumas das linhas do lance, você pode marcar apenas essas linhas. Além disso, você pode aceitar o lance de um fornecedor para algumas linhas de uma RFQ e atribuir outras linhas de RFQ a um fornecedor diferente. No entanto, você deve fazer um lance por vez.  
    - Se as linhas alternativas estiverem presentes, você poderá aceitar a linha de oferta original ou sua alternativa, mas não ambas.  
3. Selecione **Rejeitar**.
4. Selecione **Parâmetros** e, no campo **Motivo da rejeição**, insira ou selecione o motivo de rejeição do lance. O motivo é armazenado na resposta.  
5. Selecione **OK**.
6. Selecione **OK**.

## <a name="accept-a-bid"></a>Aceitar uma oferta

1. Selecione o lance a ser aceito e depois selecione o link no campo **Solicitação de cotação**. Se estiver na página **Comparar respostas de solicitação de cotação**, o lance em destaque com foco é o lance que o sistema considerará durante a ação Aceitar. Você pode aceitar linhas de apenas um lance por vez.  
2. No Painel de Ação, selecione **Responder**.
3. Selecione **Aceitar**. Se você marcou apenas linhas específicas, a ação Aceitar incluirá apenas essas linhas. Se deseja aceitar todas as linhas do lance, você não precisará marcar as linhas.  
4. Selecione **Parâmetros** e, no campo **Motivo da aceitação**, insira ou selecione o motivo de aceitação do lance. O motivo é armazenado no lance.  
5. Selecione **OK**.
6. Selecione **OK**. Ao selecionar **OK**, uma ordem de compra é gerada com base nas linhas incluídas na aceitação da RFQ. Se houver outros lances que não tenham sido processados (aceitos, rejeitados ou retornados), o sistema solicitará que você os rejeite.  

## <a name="view-the-purchase-order-that-is-generated"></a>Ver a ordem de compra gerada

No Painel de ações, na guia **Geral**, selecione **Ordem de compra**. A página que aparece mostra a ordem de compra que foi gerada quando você aceitou o lance.
