---
title: "Configurar letras de câmbio"
description: "Este tópico descreve as etapas para configurar letras de câmbio."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Configurar letras de câmbio

Este tópico descreve as etapas para configurar letras de câmbio.

Uma letra de câmbio é uma ordem por escrito ou eletrônico de um cliente especificando que outra parte, geralmente um banco, deve pagar um valor declarado à empresa. Quando uma letra de câmbio é usada como pagamento para uma nota fiscal de ordem de venda ou nota fiscal de texto livre, você credita a conta de cliente. Esse crédito é segurado pela letra de câmbio até o cliente pagar a letra de câmbio para o banco. Normalmente, você liquida a nota fiscal com a letra de câmbio a data de vencimento. Ao receber uma notificação do banco de que a letra de câmbio foi liquidada, você pode fechar a letra de câmbio. Você pode emitir uma letra de câmbio pelo banco em qualquer um destes: tempo

-   Na data de vencimento. Esta abordagem é conhecida como remeter para cobrança.
-   Antes da data de vencimento, tipicamente na data do desconto especificada em termos de pagamento configurados para o cliente. Ao lançar a transação, o valor de desconto é lançado em uma conta de despesas. O valor restante é uma responsabilidade sua até que o banco receba o pagamento do cliente. Esta abordagem é conhecida como remeter para desconto.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Configurar perfis de lançamentos para letras de câmbio
Use perfis ** de postagem de clientes ** a página para configurar os perfis de postagem que você pode usar com as letras de câmbio, protestar letras de câmbio, remessas para cobrança, e remessas para desconto. ** O conta resumo ** campo, selecione a conta resumo para lançar valores de letra de câmbio. Essa conta é debitada creditada ou, dependendo do tipo de transação de letra de câmbio:
-   Para as letras de câmbio, essa conta é debitada quando uma letra de câmbio é lançada, e creditou quando uma remessa para desconto ou remessa para cobrança é lançada.
-   Para as letras de câmbio protestadas, essa conta é debitada quando uma letra de câmbio protestada é lançada.
-   Para as remessas para cobrança, essa conta é debitada quando uma remessa para cobrança é lançada.
-   Para remessas para desconto, essa conta é debitada quando uma remessa para desconto é lançada.

** O conta de acordo ** campo, selecione a conta de caixa para lançar valores de letra de câmbio. Essa conta é debitada quando a letra de câmbio é liquidada. ** Em pagamentos antecipados de impostos ** campo, selecione a conta resumo na qual os valores de imposto sobre vendas quando as letras de câmbio são usadas para pagamentos antecipados. ** O passivo para conta de desconto gera **, selecione a conta para lançar o valor de desconto para remessas para desconto a. Essa conta é creditada quando a remessa para desconto é lançada.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Configurar parâmetros de contas a receber para letras de câmbio
** Parâmetros de contas a receber ** na página, os perfis padrão de postagem de letras de câmbio são inseridos ** razão e impostos ** na guia. As sequências numéricas são definidas ** ** sequências numéricas na guia.
Configurar nomes de diário para letras de câmbio
------------------------------------------

** Nomes de diários ** na página, crie pelo menos cinco nomes de diário a serem usados para letras de câmbio. Eis tipos de diário:
-   ** Letra de câmbio emitida de cliente ** – crie um nome do diário de letra de câmbio emitida.
-   ** Letra de câmbio protestada por cliente ** – crie um nome do diário de letra de câmbio protestada.
-   ** O cliente reemitir a letra de câmbio ** – criar um nome do diário de letras de câmbio reemitidas.
-   ** Remessa bancária de cliente ** – crie um nome do diário de remessa.
-   ** Letra de câmbio liquidada de cliente ** – crie um nome do diário de letra de câmbio.

Na página de comprovante de diário para cada diário de letra de câmbio, insira informações sobre a letra de câmbio ** letra de câmbio ** na guia. Depois que as linhas de diário de letra de câmbio forem lançadas, será possível exibir-las ** consulta de diário de letra de câmbio ** na página e estatísticas ** de letras de câmbio ** na página.
Configurar métodos de pagamento para letras de câmbio
-----------------------------------------------

** ** Métodos de pagamento na página, configure pelo menos um método de pagamento para letras de câmbio. Se você fizer negócios com mais de um banco, configure um método de pagamento que corresponde ao formato de remessa que requer cada banco para letras de câmbio.
Configurar taxas de pagamento para letras de câmbio
-----------------------------------------

Uma taxa de pagamento é um encargo associado ao processo de cobrança de pagamentos de clientes. Várias linhas de configuração de taxa de pagamento podem ser associadas cada taxa de pagamento. Você pode usar as linhas de configuração para controlar como os de valores padrão para taxas de pagamento são calculados. Por exemplo, você pode criar linhas de configuração para métodos de pagamento, especificações de pagamento, moedas, e períodos de tempo. Você também pode criar linhas de configuração para uma porcentagem ou valor com base em intervalos de dias. Por exemplo, você pode configurar uma porcentagem de juros com base no tempo que um pagamento está vencido. Se as taxas diferentes de encargos do banco para remessas diferentes, como tipos ** cobrança ** ou ** desconto **, configure uma linha de taxa de pagamento separada para cada tipo de remessa.
Configurar taxas de remessa para arquivos de remessas bancárias
------------------------------------------------

** Contas bancárias ** na página, pode configurar taxas de remessa que os encargos do banco para cada arquivo de remessa que é gerada. As taxas de remessa são lançadas quando a remessa é confirmada e os valores de taxa realizados são conhecidos. As taxas de remessa são diferentes taxas de pagamento, que são cobradas de clientes e anexadas a linhas de diário.
Configurar layouts de documento para letras de câmbio
---------------------------------------------

** Contas bancárias ** na página, clique em configuração ** **, e especifique o layout de documento necessário para cada conta bancária para as quais serão geradas documentos impressos de letras de câmbio.
Configurar clientes para letras de câmbio
--------------------------------------

** Em clientes, pagine-o ** para cada cliente que concordou em pagar usando uma letra de câmbio, poderá configurar um método de pagamento padrão para letras de câmbio de liquidação padrão ** ** na guia.




