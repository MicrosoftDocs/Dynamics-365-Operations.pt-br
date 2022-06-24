---
title: Configurar opções para automação de fatura de fornecedor (Versão preliminar)
description: Este artigo descreve as opções disponíveis para definir e configurar a automação de fatura de fornecedor.
author: sunfzam
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 86ad68b3dc08bf2c57ab5f9bc6c65bc37c0901e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874831"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>Configurar opções para automação de fatura de fornecedor

[!include [banner](../includes/banner.md)]

Este artigo descreve as opções disponíveis para definir e configurar a automação de fatura de fornecedor. Os recursos de automação de fatura usam os seguintes tipos de parâmetros de configuração:

- Parâmetros para aplicar automaticamente pagamentos antecipados em faturas importadas.
- Parâmetros para enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho e conciliar linhas de recebimento de produtos lançadas para linhas de fatura de fornecedor pendentes.
- Parâmetros para processamento de tarefas de automação em segundo plano. A estrutura de automação de processos é usada para enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho. Também é usado para fazer a correspondência automática das linhas de recebimento de produtos lançadas em linhas de fatura de fornecedor pendente e para executar a validação da conciliação de faturas para faturas manuais que foram correspondidas automaticamente nas linhas de recebimento de produtos. Processos comerciais diferentes usam essa estrutura para definir a frequência de execução de um processo selecionado. As frequências disponíveis para os processos em segundo plano **Conciliar recebimento do produto com linhas da fatura** e **Enviar faturas do fornecedor para fluxo de trabalho** incluem **Hora** e **Diariamente**.

Para configurar ou exibir informações sobre uma tarefa em segundo plano, Acesse **Administração do sistema \> Configuração \> Processar automações** e selecione a guia **Tarefa em segundo plano**.

Para obter automação sem contato do processo de importação por meio do lançamento de fatura de fornecedor, você deve configurar um Fluxo de trabalho de fatura de fornecedor. Para configurar um fluxo de trabalho, Acesse **Contas a pagar > Configurar > Fluxos de trabalho do contas a pagar**. Para garantir que a fatura possa ser processada do início ao fim sem intervenção manual, você deve incluir uma tarefa de lançamento automatizada na configuração do fluxo de trabalho.

## <a name="parameters-for-automatically-applying-prepayments-in-imported-invoices"></a>Parâmetros para aplicar automaticamente pagamentos antecipados em faturas importadas

- **Aplicar pagamento antecipado automaticamente para faturas importadas** – quando essa opção for definida como **Sim**, o sistema pesquisará automaticamente pagamentos antecipados existentes para uma ordem de compra correspondente quando as faturas de fornecedor forem importadas. Se houver pagamentos antecipados que possam ser aplicados, uma linha adicional será adicionada para aplicar os pagamentos antecipados às faturas do fornecedor que estão sendo importadas.
- **Bloquear o processo de automação de acompanhamento no caso de falha do aplicativo de pagamento antecipado** – quando essa opção for definida como **Sim**, as faturas serão bloqueadas se um pagamento antecipado não puder ser aplicado. Como outros processos automatizados, como o processo de correspondência de recebimento e o envio a um processo de fluxo de trabalho, o processo de automação de fatura não pega as faturas bloqueadas até que o pagamento antecipado seja aplicado manualmente. 

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Parâmetros para enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho

Parâmetros específicos são usados para enviar faturas de fornecedor importadas para o sistema de fluxo de trabalho. Além disso, alguns parâmetros são usados para conciliar linhas de recebimento de produtos lançadas em linhas de fatura de fornecedor pendentes. Na guia **Automação de fatura de fornecedor** da página **Parâmetros de contas a pagar**, os parâmetros que devem ser definidos são divididos entre as seções a seguir:

- Fluxo de trabalho de faturas de fornecedor
- Conciliar recebimentos de produtos automaticamente

Estão disponíveis os seguintes parâmetros:

- **Enviar faturas importadas automaticamente para o sistema de fluxo de trabalho** – se você definir esta opção como **Sim**, as faturas importadas serão enviadas automaticamente para o sistema de fluxo de trabalho. Se esta opção for definida como **Não**, as faturas deverão ser enviadas manualmente. Ao definir esta opção como **Sim**, você habilita um processo sem contato dos resultados da importação ao lançar.

    Você pode definir esta opção como **Sim** somente se um fluxo de trabalho da fatura de fornecedor ativo for configurado para sua entidade legal. Para configurar um fluxo de trabalho, Acesse **Contas a pagar \> Configuração \> Fluxos de trabalho de contas a pagar**.

- **Conciliar recebimentos de produtos a linhas da fatura antes de enviar automaticamente** – se você definir esta opção como **Sim**, a fatura importada não poderá ser automaticamente enviada para o sistema de fluxo de trabalho até a quantidade de recebimento de produtos conciliada seja igual à quantidade da fatura. Ao configurar esta opção como **Sim**, você habilita a conciliação automática de recebimentos de produtos lançados para linhas da fatura para as quais uma política de conciliação tripla está definida. Esse processo será executado até que a quantidade de recebimento de produtos conciliada seja igual à quantidade da fatura. Nesse ponto, a fatura é enviada automaticamente para o sistema de fluxo de trabalho.

    A opção **Conciliar recibos de produtos a linhas da fatura antes de enviar automaticamente** fica disponível somente se a opção **Habilitar validação da conciliação de faturas** for selecionada. Quando esta opção é selecionada, a opção **Conciliar recebimentos do produto automaticamente para linhas da fatura** é selecionada automaticamente.

- **Exigir que os totais calculados sejam iguais aos totais importados para envio automático do fluxo de trabalho** – se você definir esta opção como **Sim**, a fatura não poderá ser automaticamente enviada para o sistema de fluxo de trabalho até que os totais calculados para a fatura sejam iguais aos totais importados. Se esta opção for definida como **Não**, a fatura poderá ser automaticamente enviada para o sistema de fluxo de trabalho, mas não poderá ser lançada até que os totais calculados sejam corrigidos para que correspondam aos totais importados. Se você não importar o valor da fatura ou o valor do imposto sobre vendas, essa opção deverá ser definida como **Não**.
- **Coincidir automaticamente os recebimentos de produtos para as linhas da fatura** – se você definir esta opção como **Sim**, o processamento em segundo plano poderá ser usado para fazer a correspondência automática de recebimentos de produtos lançados em linhas da fatura para as quais uma política de conciliação tripla está definida. Esse processo será executado até que a quantidade de recebimento de produtos conciliada seja igual à quantidade da fatura ou até que o valor do campo **Número de tentativas de conciliação automática** seja obtido. O processo pode ser executado até que a fatura tenha sido enviada para o sistema de fluxo de trabalho.

    Esta opção só estará disponível se a opção **Habilitar validação da conciliação de faturas** for selecionada.

    Se você definir a opção **Conciliar recebimentos de produtos a linhas da fatura antes de enviar automaticamente** como **Sim**, essa opção não poderá ser definida como **Não**. Para definir esta opção como **Não**, é necessário definir primeiro a opção **Conciliar recebimentos de produtos a linhas da fatura antes de enviar automaticamente** como **Não**.

- **Número de tentativas de conciliação automática** – Selecione o número de vezes que o sistema deve tentar coincidir os recebimentos de produtos em uma linha da fatura antes de concluir que o processo falhou. Quando o número de tentativas especificado é atingido, a fatura é removida do processamento da automação.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
