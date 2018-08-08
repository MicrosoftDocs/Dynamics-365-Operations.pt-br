---
title: Cartas de garantia
description: "Este artigo fornece informações sobre as cartas de garantia. Em uma carta de garantia, um banco concorda em pagar um valor específico de dinheiro a uma pessoa se um dos padrões de clientes do banco em um pagamento ou obrigação àquela pessoa."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c3d61bbfdd6a304a7bd2edd81e51e556a4955dce
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="letters-of-guarantee"></a>Cartas de garantia

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre as cartas de garantia. Em uma carta de garantia, um banco concorda em pagar um valor específico de dinheiro a uma pessoa se um dos padrões de clientes do banco em um pagamento ou obrigação àquela pessoa. 

Uma carta de garantia é um contrato de um banco (o fiador) para pagar um valor definido para outra pessoa (o credor), se o cliente do banco (o principal) não cumprir um pagamento ou uma obrigação ao beneficiário. As notas de garantia não são transferíveis. Só se aplicam ao beneficiário que é mencionado no contrato. O principal pode solicitar um aumento ou uma redução no valor de uma carta de garantia, sujeito às condições do contrato. 

Para liquidar uma carta de garantia, o beneficiário deverá enviar a carta de garantia original e informar ao banco o não cumprimento do principal antes da data de vencimento. O banco paga o valor devido à conta do beneficiário, de acordo com os termos na carta de garantia. O banco reserva uma porcentagem de pagamento como margem. A porcentagem é acordada e especificada nas condições do contrato. 

Você pode criar um código para rastrear a finalidade de uma carta de garantia. Você também pode especificar os motivos que podem ser associados a uma carta de garantia quando a carta é cancelada. Você pode exibir os códigos de finalidade e os motivos do banco nas páginas **Códigos de finalidade do pagamento** e **Motivos do banco**. 

Você pode usar a página **Carta de garantia** para concluir essas tarefas:

-   Criar entradas do razão corretas e eliminar a entrada manual.
-   Registrar todas as transações monetárias e não monetárias e rastrear saldos de cartas de garantia.
-   Registrar e rastrear o status e o vencimento das cartas de garantia.
-   Gerar um relatório que lista os bancos que estão mantendo cartas de garantia.

A tabela a seguir descreve as ações que podem ser realizadas em uma carta de garantia.

| Ação              | Finalidade                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Enviar ao banco      | Enviar a solicitação de carta de garantia para o banco.                                                                       |
| Receber do banco   | Depois que o banco concordar com a solicitação enviada, cobrar a carta de garantia do banco.                            |
| Dar ao beneficiário | Depois de receber a carta de garantia do banco, fornecê-la ao beneficiário.              |
| Aumentar o valor      | Se o portador e o principal concordarem, aumentar o valor monetário.                                                  |
| Diminuir o valor      | Se o portador e o principal concordarem, reduzir o valor monetário.                                                  |
| Estender              | Depois que você fornecer a carta de garantia ao beneficiário, aumente o período de validade, se necessário. |
| Cancelamento              | Quando a finalidade para a qual a carta de garantia foi solicitada não se aplicar, cancele o contrato.                  |
| Liquidar           | Quando o beneficiário apresentar a carta de garantia ao banco, descontá-la.                      |


Para obter mais informações, consulte os seguintes tópicos:

[Transação da carta de garantia](tasks/letter-guarantee-transaction.md)

[Configurar recursos bancários e perfis de lançamento para cartas de garantia](tasks/set-up-bank-facilities-posting-profiles.md)



