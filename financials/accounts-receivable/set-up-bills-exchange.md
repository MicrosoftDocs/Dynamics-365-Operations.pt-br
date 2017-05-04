---
title: "Configurar letras de câmbio"
description: "Este tópico descreve as etapas para configurar as letras de câmbio."
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

[!include[banner](../includes/banner.md)]


Este tópico descreve as etapas para configurar as letras de câmbio.

Uma letra de câmbio é uma ordem por escrito ou eletrônica de um fornecedor especificando que outra parte, normalmente um banco, deve pagar um valor declarado para a empresa. Quando uma letra de câmbio é usada como pagamento para uma nota fiscal de ordem de venda ou nota fiscal de texto livre, você credita a conta de cliente. Esse crédito é segurado pela letra de câmbio até o cliente pagar a letra de câmbio para o banco. A nota fiscal para a letra de câmbio será tipicamente liquidada na data de vencimento. Ao receber uma notificação do banco de que a letra de câmbio foi liquidada, você pode fechar a letra de câmbio. Você pode emitir uma letra de câmbio através do seu banco em qualquer uma das seguintes ocasiões:

-   Na data de vencimento. Essa abordagem é conhecida como remeter para cobrança.
-   Antes da data de vencimento, tipicamente na data do desconto especificada pelos termos de pagamento configurados para o cliente. Ao lançar a transação, o valor de desconto é lançado em uma conta de despesas. O valor restante é uma responsabilidade sua até que o banco receba o pagamento do cliente. Essa abordagem é conhecida como remeter para desconto.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Configurar perfis de lançamentos para letras de câmbio
Use a página **Perfis de lançamento de cliente**, para configurar perfis de lançamento que você pode usar com letras de câmbio, letras de câmbio de protesto, remessas para coleta e remessas de desconto. No campo **Conta de resumo**, selecione a conta resumo na qual devem ser lançados os valores de letra de câmbio. Essa conta é debitada ou creditada com base no tipo da transação da letra de câmbio:
-   Para as letras de câmbio, essa conta é debitada quando a letra de câmbio é lançada e é creditada quando a remessa para desconto ou remessa para cobrança é lançada.
-   Para as letras de câmbio protestadas, essa conta é debitada quando uma letra de câmbio protestada é lançada.
-   Para as remessas para cobrança, essa conta é debitada quando uma remessa para cobrança é lançada.
-   Para remessas para desconto, essa conta é debitada quando uma remessa para desconto é lançada.

No campo **Conta de liquidação**, selecione a conta de caixa na qual devem ser lançados os valores de letra de câmbio. Essa conta é debitada quando a letra de câmbio é liquidada. No campo **Pré-pagamentos de imposto**, selecione a conta resumo na qual os valores de imposto sobre vendas devem ser lançados quando as letras de câmbio são usadas para pagamentos antecipados. No campo **Responsabilidades da conta de desconto**, selecione a conta na qual deseja lançar o valor de desconto para as remessas de desconto. Essa conta é creditada quando a remessa para desconto é lançada.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Configurar os parâmetros de contas a receber para letras de câmbio
Na página **Parâmetros de contas a receber**, os perfis de lançamento predefinidos para letras de câmbio são inseridos na guia **Razão e imposto**. As sequências numéricas são definidas na guia **Sequências numéricas**.
Configurar nomes de diário para letras de câmbio
------------------------------------------

Na página **Nomes de diários**, crie pelo menos cinco nomes de diário a serem usados para letras de câmbio. Veja aqui alguns tipos de diário:
-   **Letra de câmbio emitida por cliente** – crie um nome de diário para o diário de letra de câmbio emitida.
-   **Letra de câmbio protestada por cliente** – crie um nome de diário para o diário de letra de câmbio de protesto.
-   **Letra de câmbio reemitida de cliente** – crie um nome de diário para o diário de letra de câmbio reemitida.
-   **Remessa bancária de cliente** – crie um nome de diário para o diário de remessa.
-   **Letra de câmbio liquidada por cliente** – crie um nome de diário para o diário de letra de câmbio liquidada.

Na página de comprovante de diário para cada diário de letra de câmbio, insira as informações sobre a letra de câmbio na guia **Letra de câmbio**. Depois de lançadas as linhas de diário de câmbio, você pode visualizá-las na página **Consulta do diário de letra de câmbio** e na página **Estatísticas de letras de câmbio**.
Configurar métodos de pagamento para letras de câmbio
-----------------------------------------------

Na página **Métodos de pagamento**, configure pelo menos um método de pagamento para letras de câmbio. Se você fizer negócios com mais de um banco, configure um método de pagamento que corresponde ao formato de remessa que cada banco exige para letras de câmbio.
Configurar taxas de pagamento para letras de câmbio
-----------------------------------------

Uma taxa de pagamento é um encargo associado ao processo de cobrança de pagamentos de clientes. Várias linhas de instalação de taxa de pagamento podem ser associadas a cada taxa de pagamento. É possível usar as linhas de configuração para controlar como valores padrão para taxas de pagamento são calculados. Por exemplo, você pode criar linhas de configuração para métodos de pagamento, especificações de pagamento, moedas, e períodos de tempo. Você também pode criar linhas de configuração para uma porcentagem ou valor com base em intervalos de dias. Por exemplo, você pode configurar uma porcentagem de juros com base no tempo que um pagamento está vencido. Se o banco cobrar taxas diferentes para tipos de remessas diferentes, como **Coleta** ou **Desconto**, estabeleça uma linha de taxa de pagamento separada para cada tipo de remessa.
Configurar taxas de remessa para arquivos de remessas bancárias
------------------------------------------------

Na página **Contas bancárias**, você pode configurar as taxas de remessa que um banco cobra por cada arquivo de remessa que é gerado. As taxas de remessa são lançadas quando a remessa é confirmada e os valores de taxa realizados são conhecidos. As taxas de remessa diferem das taxas de pagamento, que são cobradas dos clientes e anexadas às linhas de diário.
Configurar layouts de documento para letras de câmbio
---------------------------------------------

Na página **Contas bancárias**, clique em **Configurar**, e especifique o layout de documento necessário para cada conta bancária para as quais serão geradas documentos impressos de letras de câmbio.
Configurar clientes para letras de câmbio
--------------------------------------

Na página **Clientes**, para cada cliente que concordou em pagar usando uma letra de câmbio, você pode configurar um método de pagamento padrão para letras de câmbio na guia **Padrões de pagamento**.






