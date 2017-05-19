---
title: "Códigos de informação"
description: "Este artigo oferece uma visão geral sobre códigos informativos, grupos de códigos informativos e como usá-los."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: sijoshi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: aaf02ce5bf3af94dea12344c9bfc5c8e9be7abb9
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="info-codes"></a>Códigos de informação

[!include[banner](includes/banner.md)]


Este artigo oferece uma visão geral sobre códigos informativos, grupos de códigos informativos e como usá-los.

Os códigos de informações fornecem uma maneira de capturar dados em um registro de ponto de venda (PDV). E possível usar códigos de informações para alertar o caixa a inserir informações durante várias ações no PDV, como vendas de item, devolução de itens ou seleção de clientes. Os caixas podem selecionar a entrada de uma lista ou inseri-la como um código, número, data ou texto. É possível atribuir códigos de informações a ações de loja predefinidas, a itens de varejo, a métodos de pagamento, a clientes ou a atividades específicas do ponto de venda. É possível usar os códigos de informações para fazer o seguinte:
-   Capturar informações adicionais no momento da transação, como número do voo ou motivo de uma devolução.
-   Solicitar ao caixa para selecionar preços de produtos específicos em uma lista.
-   Vincular um subcódigo a um código de informações para solicitar que o caixa insira uma entrada ao executar uma atividade específica. Por exemplo, quando um cliente devolve um produto, é possível solicitar que o caixa pergunte porque o produto está sendo devolvido. Em seguida, será possível usar os subcódigos para exibir uma lista de motivos do qual o caixa pode selecionar.
-   Vender um produto como uma venda normal, venda com desconto ou produto gratuito.
-   Solicitar ao caixa para inserir um valor ou selecionar em uma lista de subcódigos quando a caixa registradora for aberta sem realizar uma operação de vendas.

## <a name="info-codes-group-in-retail-and-commerce"></a>Grupo de códigos informativos no varejo e no comércio
No Microsoft Dynamics 365 for Operations - Varejo, você pode criar grupos de códigos informativos. Os grupos de códigos de informações adicionam flexibilidade, permitindo a definição de códigos de informações e seu uso de maneiras mais versáteis. É possível usar grupos de códigos de informações das seguintes maneiras:
-   Definir os códigos de informações e os reutilizar facilmente. Os códigos de informações incluídos em grupos de códigos de informações não têm dependência predefinida de outros códigos de informações. É possível incluir o mesmo código de informações em vários grupos de códigos de informações e usar a priorização para apresentar os mesmos códigos de informações na ordem em que fará sentido em qualquer situação específica.
-   Vincular códigos de informações para outros códigos de informações ou grupos de códigos de informações para coletar informações sobre um produto ou uma transação, sem ter que definir um código separado de informações ou código de informações vinculado para cada cenário.

## <a name="info-code-examples"></a>Exemplos de códigos informativos
**Exemplo 1: Reutilizar códigos de informações** é possível vincular códigos de informações de forma que quando um código de informações for disparado, outro código de informações seja disparado imediatamente após ele. Por exemplo, ao vender determinados produtos, você pode solicitar que o caixa pergunte ao cliente se ele deseja comprar baterias e garantia do produto. Para outros produtos, você pode solicitar que o caixa pergunte ao cliente se ele deseja comprar baterias e coletar seu código postal. Se você criar códigos de informações vinculados para esses cenários, configure cada variação do código de informações de forma que seja solicitado ao caixa coletar as informações corretas. Se você usar grupos de códigos de informações, os códigos de informações comuns, como solicitar baterias, podem ser configurados uma vez e serem reutilizados em vários grupos de códigos de informações. Também é possível usar a priorização nos grupos de códigos de informações para identificar a ordem em que os avisos são exibidos. **Exemplo 2: Vincular códigos de informações a grupos de códigos de informações** Ao vender determinados produtos, como dispositivos móveis, sempre é necessário coletar um conjunto de informações específicas, como número de telefone, identificador de equipamento móvel (MEID) e número de série. No entanto, você também deseja coletar informações diferentes de um tablet em relação a um telefone celular. É possível configurar um grupo de códigos de informações que inclui avisos sobre o número de telefone, o MEID e o número de série e vincular o grupo de códigos de informações ao código de informações individual. Quando o código de informações específico do produto é disparado, o grupo de códigos de informações pode ser disparado ao lado para permitir a coleta de dados comuns, sem a necessidade de definir vários conjuntos de códigos de informações vinculados para cada dispositivo.

 
-






