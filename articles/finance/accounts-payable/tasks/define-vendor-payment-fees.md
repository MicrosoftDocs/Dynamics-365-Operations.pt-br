---
title: Definir taxas de pagamento de fornecedor
description: Configure taxas de pagamento de fornecedor.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c490bb4d15fa03742b12f337046f26976ab70d29
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109811"
---
# <a name="define-vendor-payment-fees"></a>Definir taxas de pagamento de fornecedor

[!include [banner](../../includes/banner.md)]

Configure taxas de pagamento de fornecedor. Esta tarefa usa a empresa de demonstração USMF.

1. Acesse **Contas a pagar > Configuração de pagamento > Valor de pagamento**.
2. Clique em **Novo**.
3. No campo **ID do valor**, digite um valor.
    * O **ID do valor** deve descrever quando esse valor será usado, como "EFT_Fee".  
4. No campo **Nome**, digite um valor.
5. No campo **Descrição do valor**, digite um valor.
    * Adicione uma descrição para fornecer mais detalhes sobre quando a taxa será cobrada.  
6. No campo **Encargo**, selecione **Fornecedor** ou **Razão**.
    * Use **Razão** quando o valor será cobrado da organização. Use **Fornecedor** quando o valor for avaliado para o fornecedor.  
7. Insira uma conta principal onde a taxa será cobrada.
    * Essa opção só fica disponível quando **Razão** é selecionado como a opção **Encargo**.  
8. Selecione o diário em que a taxa pode ser usada. 
    * Para uma taxa de pagamento de fornecedor, você selecionaria o diário de 'Pagamento fornecedor'.  
9. Clique em **Salvar**.
10. Clique em **Configuração de taxa de pagamento**.
    * Prossiga para a **Configuração do valor de pagamento** para definir quando o valor deverá ser padronizado como o diário selecionado.  
11. Selecione **Tabela**, **Grupo** ou **Tudo**.
    * **Tabela** é usada para selecionar uma única conta bancária, **Grupo** é usado para selecionar um grupo de bancos e **Tudo**, como configuração de valor para todas as contas bancárias.  
12. Selecione um grupo de bancos ou uma conta bancária.
    * A consulta mostrará o grupo de bancos se você selecionou **Grupo** e contas bancárias se você selecionou **Tabela**.  
13. Selecione o método de pagamento a ser usado por essa taxa.
14. Selecione a **Especificação de pagamento** para a forma de pagamento selecionada.
    * A **Especificação de pagamento** é usada com as formas de pagamento de transferência eletrônica de fundos.  
15. Selecione se a taxa é uma porcentagem, um valor ou um intervalo.
16. Inserir o percentual do valor da taxa.
    * Se o **Valor** for uma porcentagem, insira a porcentagem. Se o **Valor** for uma quantidade, insira o valor. Se o **Valor** for um intervalo, use a guia **Intervalo** para definir os valores diferenciados.  
17. No campo **Moeda do valor**, selecione a moeda em que o valor será avaliado.
    * Esta moeda é para a taxa. A moeda do pagamento é usada para definir quando a regra de taxa deverá ser cobrada com base na moeda do pagamento. Por exemplo, seu banco pode cobrar uma taxa quando um pagamento é efetuado em Euro, mas todos pagamentos restantes não são avaliados por uma taxa.  
18. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
