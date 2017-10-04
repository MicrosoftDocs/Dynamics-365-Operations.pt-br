--- 
title: "Estabelecer método de pagamento de clientes"
description: "Criar um método de pagamento para pagamentos de clientes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bfafcccb12112ca7cceefb65be3f942bfc307751
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-method-of-payment"></a>Estabelecer método de pagamento de clientes

[!include[task guide banner](../../includes/task-guide-banner.md)]

Criar um método de pagamento para pagamentos de clientes. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento.
2. Clique em Novo.
3. No campo Método de pagamento, insira um ID para o método de pagamento.
    * O método da ID de pagamento é mostrado nas notas fiscais e pagamentos, para que o torne descritivo suficiente para compreender o tipo de pagamento que está sendo registrado, e para a conta bancária.  
4. No campo Descrição, insira uma descrição.
5. Selecionar o status de pagamento é necessário para que os pagamentos sejam lançados.
    * Ao criar um pagamento de cliente, ele só pode ser lançado quando o status do pagamento corresponde ao status do pagamento definido aqui.  
6. Selecione como os pagamentos de clientes devem ser criados para notas fiscais.
    * Esta opção é usada apenas para executar uma proposta de pagamento. Uma proposta de pagamento pode ser usada para pagamentos de cliente ao fazer os débitos diretos, e o recebimento dos fundos das contas bancárias dos clientes.  
7. Selecionar o tipo de pagamento.
    * O tipo de pagamento ajudará a determinar se qualquer validação ocorre ou não no pagamento.  
8. Selecione quais tipos de pagamentos de conta serão lançados.
    * Normalmente, o banco deve ser selecionado para essa opção.  
9. Selecione a conta bancária na qual o pagamento será registrado.
10. Insira o tipo de transação bancária para identificar o tipo de pagamento usado pelo banco.
    * O tipo de transação bancária será usado durante o processo de reconciliação do banco, e pode facilitar a reconciliação.  
11. Selecione se o pagamento será lançado temporariamente em uma conta de transição.
    * Se desejar testar o tempo de flutuação para que um pagamento desmarque o banco, use a funcionalidade de construção de transição. O pagamento será lançado temporariamente em uma conta contábil até que o banco a desmarque quando o pagamento se moverá à conta bancária como definido aqui.  
12. Insira a conta principal usada para lançar o lançamento de transição.
    * Esta é a conta principal a qual o pagamento será lançado se temporariamente usar a construção de transição.  
13. Use a guia do formato de arquivo para definir a configuração de pagamentos eletrônicos.
14. Use a guia do controle de pagamento para definir os campos que são obrigatórias.
    * Por exemplo, caso você precise de todos os pagamentos com este método de pagamento a serem depositados, você pode escolher essa opção nesta guia.  
15. Use a guia Atributos de pagamento para definir os atributos de pagamento que deseja usar para o método de pagamento.
16. Clique em Salvar.

